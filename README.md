# Paper by Spread Zhao

感谢Xduts的作者：[note286/xduts: Xidian University TeX Suite 西安电子科技大学LaTeX套装](https://github.com/note286/xduts)

本仓库基于Xduts的编译产物进行。安装了Tex发行版之后就可以一键使用。我的工作本身也不是很多。。。

## 使用方式

> 由于大家的电脑大部分都是Windows，我就不介绍Linux的安装方式了。其实都非常简单，可以参考TexLive的官网：[TeX Live - TeX Users Group](https://www.tug.org/texlive/)

1. 下载TexLive: https://mirror.ctan.org/systems/texlive/tlnet/install-tl-windows.exe
2. 安装方式参考：[Windows - TeX Live - TeX Users Group](https://www.tug.org/texlive/windows.html)
3. 安装完之后，就应该有环境变量了（Linux用户这一部需要手动添加）。我们这个工程需要的是xelatex和biber这两个程序。可以自己试一试在终端里输入看能不能得到版本信息，证明安装好了：

    ```shell
    xelatex --version
    biber --version
    ```

4. 如果都装好了，就搞定了。clone本仓库，其中的
    1. `build.sh`：Linux用户构建pdf；
    2. `build.bat`：Windows用户构建pdf；
    3. `clear.sh`：Linux用户清除构建出的产物；
    4. `clear.bat`: Windows用户清除构建出的产物。

    > 其实你也可以点进脚本看一看，都没什么东西。这个脚本的编写参考了[The Short Introduction to LaTeX2e (Chinese Simplified)](https://mirrors.cloud.tencent.com/CTAN/info/lshort/chinese/lshort-zh-cn.pdf)的6.1.4小节的最后一部分。