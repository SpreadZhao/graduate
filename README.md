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

    > 其实你也可以点进脚本看一看，都没什么东西。这个脚本的编写参考了 [The Short Introduction to LaTeX2e (Chinese Simplified)](https://mirrors.cloud.tencent.com/CTAN/info/lshort/chinese/lshort-zh-cn.pdf) 的6.1.4小节的最后一部分。

5. `hello.tex`是主文档。仿照文档中的写法来进行就可以。
6. 写论文的方式可以参考 [Xduts的文档](docs/xduts.pdf)。

## Trouble Shooting

### 编译时出现字体缺失

目前我看下来，需要这些字体：

- Arial
- Consolas
- SimHei
- SimKai
- SimSun
- Time New Romans

缺什么装什么就行。

### libcrypt.so 报错

[dlopen: libcrypt.so.1: cannot open shared object file: No such file or directory](https://stackoverflow.com/questions/71187944/dlopen-libcrypt-so-1-cannot-open-shared-object-file-no-such-file-or-directory)

### 添加图片

使用类似 https://app.diagrams.net/ 进行画图时，导出的图片如果是 png 的话，感觉很糊；如果是 svg 的话，不好加进去。所以导出 pdf 格式，并参考：https://blog.csdn.net/qq_37085158/article/details/128875888 的最后面，使用 pdfcrop 工具剪裁：

```shell
# pdfcrop 工具 TexLive 环境安装就有，在安装的时候就应该和 xelatex, biber 一同添加到环境变量里了。
pdfcrop haha.pdf
```

之后在原目录就会生成一个已经剪裁好的pdf，最后这么添加：

```tex
\begin{center}
\begin{adjustbox}{max width=\textwidth}
\includegraphics{assets/visibility-dispatch-framework.pdf}
\end{adjustbox}
\end{center}
```

具体的排版依然可以参考 [The Short Introduction to LaTeX2e (Chinese Simplified)](https://mirrors.cloud.tencent.com/CTAN/info/lshort/chinese/lshort-zh-cn.pdf)。