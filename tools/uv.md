# Python虚拟环境工具uv使用指南

## 简介
uv是Astral公司开发的极速Python虚拟环境和包管理工具，比virtualenv/venv快10-100倍。

## 安装
```bash
# pip安装
pip install uv

# On macOS and Linux.
curl -LsSf https://astral.sh/uv/install.sh | sh

# On Windows.
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"


# brew install & upgrade
$ brew install uv # install
$ brew upgrade uv # upgrade
```

## 创建虚拟环境
```bash
# 创建名为.venv的虚拟环境
uv venv
```

## 激活虚拟环境
```bash
# Linux/macOS
source .venv/bin/activate

# Windows
.\.venv\Scripts\activate
```

## 退出虚拟环境
```bash
deactivate
```

## 包管理
```bash
# 安装包
uv pip install package_name

# 安装开发依赖
uv pip install -e .

# 导出requirements
uv pip freeze > requirements.txt

# 从requirements安装
uv pip install -r requirements.txt
```

## 项目初始化
```bash
# 初始化新Python项目
uv init my_project

# 从现有项目初始化
uv init .

# 初始化并创建虚拟环境
uv init --venv my_project
```

## 删除虚拟环境
```bash
rm -rf .venv  # Linux/macOS
del /s /q .venv  # Windows
```

## 性能优势
1. 虚拟环境创建速度快10-100倍
2. 包安装速度快10-100倍
3. 完全兼容pip命令
4. 支持Python 3.7+
5. 跨平台支持

## 最佳实践
- 项目根目录创建.venv
- 将.venv加入.gitignore
- 使用uv pip替代原生pip

## References
* https://github.com/astral-sh/uv