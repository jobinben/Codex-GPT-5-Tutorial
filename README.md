# 2025年最新的 Codex-GPT-5 国内安装和使用的教程，如何设置中文回复等教程，ChatGPT Plus 代充值等教程

前段时间的 GPT-5-Codex 更新之后，越来越多的人开始用起来了 OpenAI 家的 Codex 了，因为用的人多了，也开始有很多伙伴咨询我怎么使用 Codex。 

今天有空，来更新一篇关于 Codex 常用场景的功能介绍 和 安装使用过程的注意点。

## 一、什么是 Codex ?

Codex 是 OpenAI 最新推出的编程工具，它有云端的 Codex Web，也有本地的终端版本 Codex CLI。

**而且最新的 GPT-5-Codex 模型在大型复杂任务上能够一次独立工作超过 7 小时！**

AI编程有很多种工具，有IDE的、有CLI的、也有云端版的。 比如大家都熟悉的 Cursor 就是 AI IDE 编辑器、**而 Codex 是跟 Claude Code、Gemini CLI 这些都有CLI的。**

**为什么不选择 Claude Code 了？** 因为 Claude Code 最近经常降智、而且 Claude 容易封号，大多伙伴都是直接使用 Claude Code 镜像的。

而 Codex 封号情况没有那么糟糕，而且 ChatGPT Plus 订阅版比较便宜，几乎人手一个，大家随时都可以测试 Codex 。


## 二、如何安装 Codex ？

Codex 它可以直接在 ChatGPT 网页上使用，也可以直接在本地安装对应的 Codex CLI。

**Codex 也可以直接在 VS Code IDE 上安装对应的扩展插件，UI看起来就是在使用 Cursor 一样。**

![](https://files.mdnice.com/user/41479/9eb74ac9-cc41-4c12-88c3-500a03771e30.png)



### 2.1 方式一：在 IDE 上使用 Codex

**哪些 IDE 工具支持 Codex 扩展呢？** 你可以在 VS Code、Cursor、Windsurf 等，搜索对应的 Codex 插件就可以看到官方的Codex。

下面我就以 VS Code IDE 为例子教大家怎么安装。

首先，打开你的IDE，在插件市场搜索 Codex ，注意识别是 OpenAI 的标志的 Codex，不然你会安装到其他插件去了。


![](https://files.mdnice.com/user/41479/d4e1bed6-243f-4d4a-81dd-8bed13e3afce.png)


安装之后，你就可以在你的IDE右上方看到 OpenAI 的Logo，你也可以在侧边栏直接唤醒你的 Codex。

![](https://files.mdnice.com/user/41479/dbba1337-7e30-404c-ade8-46658d58434d.png)

比如你要改什么文件，或者想做什么，直接在输入框输入即可，另外也可以切换你的模型，平时我都是直接使用 GPT-5-Codex（high）。


![](https://files.mdnice.com/user/41479/6d42d4fb-9461-4fdb-b4cc-b42919d42c99.png)


对于小白来说，你直接在 IDE 安装 Codex 是最方便的了。 而且操作都是有 GUI 界面，降低了上手难度。

### 2.2 方式二：在终端使用 Codex CLI

Codex CLI 是一个编码代理，您可以从终端本地运行，并且可以在计算机上读取、修改和运行代码。

如果你是 MacBook 用户，直接安装 Codex CLI 就行，随时都可以调起你的 Codex 进行 AI 编程。

**因为目前的 Codex CLI 支持在 macOS 和 Linux。Windows 仍处于实验阶段，建议在 WSL 中运行。**

你直接在 Windows 安装的话，会出现一些乱码甚至各种奇怪的麻烦，处理这些问题估计一整天就要过去了。

**Codex CLI 两种安装方式：npm 和 Homebrew。**

（1）使用 npm 的话, 需要先安装一下 NodeJS 环境。

如果系统是 Ubuntu / Debian 的 Linux用户，可以使用下面的命令安装Node.js：

```shell
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo bash -
sudo apt-get install -y nodejs
node --version
npm --version
```

如果系统是 MacOS 的用户，可以用下面的命令安装Node.js：

```shell
sudo xcode-select --install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
sudo brew install node
node --version
```

确保你的 npm 和 Nodejs可以使用时，就可以通过以下命令安装 Codex CLI：

```shell
npm install -g @openai/codex
```

（2）使用 Homebrew 安装 Codex：

```shell
brew install codex
```

**两种方式，选择其中之一就行，我是已经有NodeJS环境，所以就用第一种方式进行安装了。**

安装之后，创建一个目录，然后在目录下开启你的终端，执行 `codex` 就可以唤醒 Codex CLI 。

![](https://files.mdnice.com/user/41479/88b9df82-a9e8-4516-9564-ef3a01cdeb95.png)

## 三、Codex CLI 的使用分享

在使用 Codex CLI，大家可能会出现跟我一样的疑惑或者问题，都可以参考以下方式解决。

### 3.1 如何设置 Codex 以中文回复

这个你可以直接在终端告诉它一直使用中文回复，但是重启之后可能就失效了。所以你可以通过 Codex 特殊的记忆文件：`AGENTS.md`。

你可以在当前目录，执行 `/init` 它就会在当前工作空间生成。 但是不符合我们的场景，我们需要全局的，那么可以跟我这样子操作。

在 `~/.codex/` 下 创建一个 `AGENTS.md` 文件，然后输入 **"Always respond in Chinese-simplified"** 在里面。

你也可以复制以下指令，在你的终端执行即可：

```shell
mkdir -p ~/.codex && printf 'Always respond in Chinese-simplified\n' > ~/.codex/AGENTS.md
```

### 3.2 如何切换和查看当前模型

执行 `/model` 就可以切换和查看自己正在使用的模型，优先推荐 GPT-5-Codex (high)。

```shell
/model
```

### 3.3 本地如何启动登录授权 Codex CLI

本地的话，大家一定要记得开启全局路由，也就是你魔法的Tun模式！最近太多人使用 Codex 了，OpenAI 的算力负载也提高了很多，所以可能会检测一些滥用的用户进行封号。

避免这种情况，建议在你的魔法（TZ）工具上，开启对应的全局 Tun 模式。


![](https://files.mdnice.com/user/41479/adbbdf26-2d4e-4d0d-a055-0f5747065d3b.png)


## 四、Codex CLI 哪些用户可以使用？

Codex 目前只能给订阅了 GPT 会员的用户才能使用，如果你不知道这么升级自己的 GPT Plus 的话，可以使用下方的一键升级：

> **GPT一键升级：https://upchatgpt.com**


![](https://files.mdnice.com/user/41479/c3ec582b-01f1-4533-8e19-77ecd641142f.png)


**不知道怎么使用的话，看官网的教程即可，很简单 2 分钟就搞定 GPT 的升级。**


## 五、Windows 上安装 WSL 使用 Codex CLI

### 5.1 安装WSL，必须满足以下要求：

- Windows 11 或 Windows 10 21H2以上，专业版/工作站版/企业版（非家庭版，需支持Hyper-V）

- CPU 需支持且已在 BIOS/UEFI 中启用虚拟化

### （1）按照以下步骤安装WSL：

安装之前需要打开虚拟化，否则过程会出现未知的错误。

打开路径：`控制面板 -> 程序与功能 -> 打开或关闭 Windows 功能` 启动以下功能：

  - Virtual Machine Platform（虚拟机平台）
  - Windows Subsystem for Linux Support（WSL）
  

**下载和安装对应版本的 WSL，** 选择您的系统版本，复制到浏览器进行下载 WSL 安装包:

  - 64-Bit WSL-2.5.9.0 [推荐]
  ```url
  https://vip.123pan.cn/1831946356/links/wsl.2.5.9.0.x64.msi
  ```

  - ARM64 WSL-2.5.9.0
  ```url
  https://vip.123pan.cn/1831946356/links/wsl.2.5.9.0.arm64.msi
  ```

  - ARM64_MicrosoftStore WSL-2.5.9.0
  ```url
  https://vip.123pan.cn/1831946356/links/Microsoft.WSL_2.5.9.0_x64_ARM64.msixbundle
  ```
**你也可以不用上面的安装包，直接访问 GitHub 安装最新的版本：**

> https://github.com/microsoft/WSL/releases


### （2）安装虚拟机：

安装完WSL之后，你可以在微软应用商店中安装最新的Ubuntu 24.04 LTS 或者 通过以下命令安装：

```bash
wsl --install -d Ubuntu-24.04
```

**如果执行后遇到包错的情况，无法链接之类的，是因为网络问题，可以开一下魔法，或者修改一下 github 的host本地dns的解析IP。（也可以问AI）**

你也可通过 `wsl -l -o` 命令选择其他系统版本。

安装完 **Ubuntu** 之后，你可以在**终端（或PowerShell）**输入wsl访问安装的操作系统：

 - **首次用需要设置用户名和密码：**

> 如果您通过开始菜单的应用访问一次，直接关闭窗口而不输入用户名和密码，下次访问将使用root用户

  - Windows将安装的操作系统虚拟机视作一个应用，如Ubuntu 24.04 LTS 会出现在你的开始菜单
  

### （3）Windows 的 Codex CLI 安装

安装完Ubuntu之后，你只需在CMD或者终端工具上，运行`wsl`就可以进入。

```bash
wsl
```

接着，就可以在wsl下面，进行运行和部署 Codex CLI。 **安装步骤跟上面的 Ubuntu/Linux 👆 系统 安装的流程一致。**



















