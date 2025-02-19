---
sidebar_position: 2
---

# 安装

## 1. 安装 KCL

### 二进制下载

KCL 的每个版本都包含各种操作系统和体系结构。这些二进制版本可以从 [Github](https://github.com/kcl-lang/kcl/releases/) 手动下载并安装，下载完成后将 `{install-location}/kclvm/bin` 添加到环境变量 PATH 中。

#### MacOS & Linux

```bash
export PATH=$PATH:{install-location}/kclvm/bin
```

#### Windows

```powershell
$env:PATH += ";{install-location}\kclvm\bin;"
```

### 使用脚本安装最新版本

#### MacOS

将 KCL darwin 最新版本安装到 /usr/local/kclvm/bin

```bash
curl -fsSL https://kcl-lang.io/script/install.sh | /bin/bash
```

#### Linux

将 KCL linux 最新版本安装到 /usr/local/kclvm/bin

```bash
wget -q https://kcl-lang.io/script/install.sh -O - | /bin/bash
```

#### Windows

将 KCL windows 最新版本安装到 $Env:SystemDrive\kclvm\bin，并将该目录添加到用户 PATH 环境变量中。

```bash
powershell -Command "iwr -useb https://kcl-lang.io/script/install.ps1 | iex"
```

### Homebrew (MacOS)

```bash
brew install kcl-lang/tap/kclvm
```

### Scoop (Windows)

首先安装 [Scoop](https://scoop.sh/), 然后通过如下命令安装 `kcl`:

```bash
scoop bucket add kcl-lang https://github.com/kcl-lang/scoop-bucket.git
scoop install kcl-lang/kclvm
```

### 使用 Python3 安装

通过 `Python3` 和 `pip` 安装 `kcl` (Python3 要求 3.7.3+)

```bash
python3 -m pip install kclvm --user
```

添加一个 kcl 命令的别名 (可选)

```bash
alias kcl='python3 -m kclvm'
```

### 使用 Go 安装

通过 `Go` 命令安装 (Go 要求 1.18+)

```bash
go install kcl-lang.io/kcl-go/cmds/kcl-go@main
```

添加一个 kcl 命令的别名 (可选)

```bash
alias kcl='kcl-go run'
```

### 使用 Docker 镜像安装

+ 基本命令

```bash
docker run --rm -p 8080:8080 -it kusionstack/kclvm
```

+ 更新镜像

```bash
docker pull kusionstack/kclvm
```

### 注意

> ⚠️ 对于上述所有安装方式, 如果您想使用 [KCL Python 插件](https://kcl-lang.io/docs/reference/plugin/overview), 需要确保您已经安装了 Python 3.7+ 并将 python3 命令添加到您的 PATH 中

> 为了避免 GLIBC 版本过低问题, 对于低版本的 linux 发行版如 centos7, 您可以在 [Github](https://github.com/kcl-lang/kcl/releases/) 找到 kclvm-centos 版本并下载安装。

## 2. 安装 KCL IDE 插件

### VS Code

KCL 为 VS Code 本地版本和在线版本提供了插件支持。

本地 VS Code 可以安装完整的 [KCL 插件](https://marketplace.visualstudio.com/items?itemName=kcl.kcl-vscode-extension)，提供了高亮、自动补全（部分：关键字补全等）、跳转、悬停、大纲等功能。

在线版本可以从 https://vscode.dev 地址打开，然后安装“KCL for vscode.dev 插件”，效果如下:

![](/img/docs/user_docs/getting-started/install/ide-vscode.png)

### IntelliJ IDEA

从[这里](https://github.com/kcl-lang/intellij-kcl/releases)下载发行版，在 IntelliJ IDEA 中，点击 Preference -> plugins -> install Plugin from Disk... -> 选择 kcl-idea-plugin zip -> 重启 IDE。此插件需要 IntelliJ IDEA 2020.2+

## 下一步

+ [KCL 快速开始](/docs/user_docs/getting-started/kcl-quick-start)
