以下是 Anaconda 的安装及配置教程：

**一、下载 Anaconda**

1. 打开 Anaconda 官方网站（

   https://www.anaconda.com/

   ）。在官网首页，你可以看到下载链接。根据你的操作系统（Windows、macOS 或 Linux）选择对应的安装包。

   - **Windows**：通常会下载一个.exe 后缀的安装文件。
   - **MacOS**：是.pkg 后缀的安装包。
   - **Linux**：下载.sh 后缀的文件，并且安装过程可能会因为不同的 Linux 发行版而略有差异。

**二、安装 Anaconda（以 Windows 为例）**

1. 双击下载好的.exe 安装文件，启动安装向导。
2. 在安装过程中，你可以选择安装路径。不过，建议使用默认路径，以避免可能出现的路径配置问题。
3. 当提示 “Add Anaconda to my PATH environment variable”（将 Anaconda 添加到 PATH 环境变量）时，建议选择勾选此项。这一步很重要，因为它可以让你在命令提示符或 PowerShell 中方便地使用 Anaconda 相关命令。不过，在某些情况下，可能由于系统权限等问题，不勾选此项也能在后续手动配置 PATH 环境变量来解决。
4. 按照安装向导的提示完成安装，这个过程可能需要一些时间，安装完成后可能会提示你是否安装一些其他相关软件，如 VS Code 等，你可以根据自己的需求选择是否安装。

**三、验证安装（以 Windows 为例）**

1. 安装完成后，你可以通过打开 “开始” 菜单，找到 “Anaconda Prompt” 并打开它。在 Anaconda Prompt 中输入以下命令：
   - `conda --version`
   - 如果安装成功，会显示你安装的 Conda 版本号，例如 “conda 24.1.1”。

**四、配置环境（创建和管理虚拟环境）**

1. 创建虚拟环境

   - 打开 Anaconda Prompt（在 Windows）或终端（在 macOS 和 Linux）。
   - 使用以下命令创建一个新的虚拟环境。例如，创建一个名为 “myenv” 的 Python 3.10 环境：
     - `conda create -n myenv python = 3.10`
   - 这里，“-n” 参数用于指定虚拟环境的名称，“python = 3.10” 表示这个环境使用 Python 3.10 版本。你可以根据实际需要更改 Python 版本。
   - 在创建过程中，Conda 会提示你安装一些必要的包，输入 “y” 并回车来确认安装。

2. 激活虚拟环境

   - 创建好虚拟环境后，需要激活它才能使用。在 Anaconda Prompt 或终端中，输入以下命令来激活 “myenv” 环境（以 “myenv” 为例）：
     - **Windows**：`activate myenv`
     - **MacOS 和 Linux**：`source activate myenv`
   - 激活环境后，你会在命令提示符的前面看到环境名称（如 “(myenv)”），这表示你现在处于该虚拟环境中。

3. 安装和管理包

   - 在激活的虚拟环境中，可以使用

     ```
     conda install
     ```

     或

     ```
     pip install
     ```

     命令来安装需要的 Python 包。例如，要安装 NumPy 包：

     - `conda install numpy`或者`pip install numpy`

   - 如果要卸载一个包，使用

     ```
     conda remove
     ```

     或

     ```
     pip uninstall
     ```

     命令。例如，要卸载之前安装的 NumPy 包：

     - `conda remove numpy`或者`pip uninstall numpy`

4. 退出虚拟环境

   - 当你完成在虚拟环境中的操作后，可以使用以下命令退出虚拟环境：
     - **Windows**：`deactivate`
     - **MacOS 和 Linux**：`source deactivate`

这就是 Anaconda 基本的安装和配置教程，通过合理地创建和使用虚拟环境，可以更好地管理不同项目的 Python 依赖。

只用win11的，并且修改默认包的下载地址



基于 10 个搜索来源

![img](https://p3-search.byteimg.com/img/labis/d5b4fcf9a73f32c0593ff1bbb78d1930~noop.jpeg)

在 Win11 系统下修改 Anaconda 默认包的下载地址，可以按照以下步骤进行操作：

### 找到.condarc 文件

- 一般情况下，该文件默认存放在`C:\Users\[用户名]`目录下2610.

### 生成.condarc 文件

- 若在上述目录下未找到该文件，可以打开 Anaconda Prompt，输入以下命令来生成：`conda config --set show_channel_urls yes`6810.

### 修改.condarc 文件

- 用记事本或其他文本编辑器打开.condarc 文件，将其内容修改为如下形式268 ：

收起



plaintext



复制

```plaintext
channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  - defaults
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch-lts: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
show_channel_urls: true
envs_dirs:
  - [你期望的环境下载路径，如D://Anaconda//envs]
pkgs_dirs:
  - [你期望的包下载路径，如D://Anaconda//pkgs]
```

### 验证修改是否成功

- 在 Anaconda Prompt 中输入`conda info`命令，查看输出信息中的默认下载路径是否已更改为你所设置的路径26.

还要修改本地的存放位置

1. 创建新的存储目录
   - 首先，在你想要存储 Anaconda 相关文件（如环境和包）的本地磁盘分区（例如 D 盘）创建新的文件夹。假设你创建了两个文件夹：`D:\Anaconda\envs`用于存储虚拟环境，`D:\Anaconda\pkgs`用于存储软件包。
2. 修改.condarc 文件
   - 找到`.condarc`文件，通常在`C:\Users\[你的用户名]`目录下。
   - 用记事本或其他文本编辑器打开`.condarc`文件，添加或修改以下内容：

收起



plaintext



复制

```plaintext
envs_dirs:
  - D:\Anaconda\envs
pkgs_dirs:
  - D:\Anaconda\pkgs
```

- 这些设置会告诉 Anaconda 将虚拟环境存储到`D:\Anaconda\envs`目录下，将软件包存储到`D:\Anaconda\pkgs`目录下。

1. 验证修改是否成功
   - 打开 Anaconda Prompt。
   - 可以通过创建一个新的虚拟环境来验证。例如，运行命令`conda create -n test_env python=3.10`。
   - 然后检查`D:\Anaconda\envs`目录下是否出现了新创建的`test_env`虚拟环境文件夹。
   - 当你使用`conda install`命令安装软件包时，检查`D:\Anaconda\pkgs`目录下是否开始存储下载的软件包文件。

需要注意的是，修改存储位置后，在使用 Anaconda 相关命令时，要确保新的路径具有适当的读写权限。如果遇到权限问题，可能需要以管理员身份运行 Anaconda Prompt 或者调整文件夹的权限设置。

将以上总结在一起

以下是在 Win11 系统下安装 Anaconda 并修改默认包下载地址与本地存放位置的完整教程：

### 一、下载 Anaconda

1. 打开 Anaconda 官方网站（https://www.anaconda.com/），根据 Win11 系统选择对应的.exe 安装文件进行下载。

### 二、安装 Anaconda

1. 双击下载好的.exe 安装文件，启动安装向导。
2. 选择安装路径，建议使用默认路径，若有特殊需求可自行更改。
3. 当提示 “Add Anaconda to my PATH environment variable” 时，建议勾选此项以便在命令提示符或 PowerShell 中方便使用 Anaconda 相关命令。若因系统权限等问题未勾选，后续可手动配置 PATH 环境变量。
4. 按照安装向导提示完成安装，安装完成后可能会提示是否安装一些其他相关软件（如 VS Code 等），可根据自身需求选择是否安装。

### 三、修改默认包下载地址与本地存放位置

1. 找到或生成.condarc 文件

   ：

   - 一般在`C:\Users\[用户名]`目录下查找.condarc 文件。若未找到，则打开 Anaconda Prompt，输入`conda config --set show_channel_urls yes`命令来生成。

2. 修改.condarc 文件

   ：

   - 用记事本或其他文本编辑器打开.condarc 文件，将其内容修改为如下形式：

收起



plaintext



复制

```plaintext
channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  - defaults
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch-lts: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
show_channel_urls: true
envs_dirs:
  - [你期望的环境下载路径，如 D://Anaconda//envs]
pkgs_dirs:
  - [你期望的包下载路径，如 D://Anaconda//pkgs]
```

1. 验证修改是否成功

   ：

   - 在 Anaconda Prompt 中输入`conda info`命令，查看输出信息中的默认下载路径是否已更改为你所设置的路径，并且检查创建虚拟环境和安装软件包时是否存储到指定的本地目录。例如，在 Anaconda Prompt 中运行`conda create -n test_env python=3.10`命令创建一个新的虚拟环境，然后检查`D:\Anaconda\envs`目录下是否出现了`test_env`虚拟环境文件夹；使用`conda install`命令安装软件包时，检查`D:\Anaconda\pkgs`目录下是否开始存储下载的软件包文件。

注意：修改存储位置后，要确保新的路径具有适当的读写权限。若遇到权限问题，可能需要以管理员身份运行 Anaconda Prompt 或者调整文件夹的权限设置。

