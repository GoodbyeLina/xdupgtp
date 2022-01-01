# 项目名称

xdupgtp-Xidian University Postgraduate Thesis Proposal

西安电子科技大学研究生学位论文开题报告表XeLaTeX模板

# 使用/示例

本节介绍了一些使用本项目模板的方法，建议用户根据自身情况阅读。

## 字体安装

考虑到可能存在版权问题，故不提供字体文件或字体下载链接。

对于编译得到pdf文件，可以通过运行

```shell
pdffonts xdupgtp.pdf
```

来查看字体信息，包括字体名称和字体嵌入等情况。

### Windows

Windows平台无需手动配置字体，所需字体Windows操作系统已内置。

### GNU/Linux

由于默认情况下中易宋体的意大利形状对应的是中易楷体，因此中文字体除中易宋体和中易黑体外，还需要中易楷体。

用户可以从Windows操作系统字体库中拷贝出`simhei.ttf`、`simkai.ttf`、`simsun.ttc`、`times.ttf`、`timesbd.ttf`、`timesbi.ttf`和`timesi.ttf`共7个字体文件至GNU/Linux，其中三个中文字体文件位于`C:\Windows\Fonts`处，Times New Roman字体的四个字体文件位于`C:\Windows\Fonts\Times New Roman`处。用户在查找字体时，可以根据Windows中英文系统内字体名称来查找，找到后复制该字体，粘贴至某个空白文件夹即可得到对应的字体文件，然后将这7个字体文件传输至GNU/Linux。

|    字体名称     | 字体文件名  |  Windows英文系统内字体名称  | Windows中文系统内字体名称 |
| :-------------: | :---------: | :-------------------------: | :-----------------------: |
|    中易黑体     | simhei.ttf  |       SimHei Regular        |         黑体 常规         |
|    中易楷体     | simkai.ttf  |        KaiTi Regular        |         楷体 常规         |
|    中易宋体     | simsun.ttc  |       SimSun Regular        |         宋体 常规         |
| Times New Roman |  times.ttf  |   Times New Roman Regular   |   Times New Roman 常规    |
| Times New Roman | timesbd.ttf |    Times New Roman Bold     |   Times New Roman 粗体    |
| Times New Roman | timesbi.ttf | Times New Roman Bold Italic |  Times New Roman 粗斜体   |
| Times New Roman | timesi.ttf  |   Times New Roman Italic    |   Times New Roman 斜体    |

使用如下命令在GNU/Linux安装字体：

```shell
sudo cp simhei.ttf simkai.ttf simsun.ttc times.ttf timesbd.ttf timesbi.ttf timesi.ttf /usr/share/fonts
```

然后就可以根据[编译](#编译)里的方法去编译了。

### macOS

参考[GNU/Linux](#gnulinux)从Windows平台提取字体文件，然后在macOS上双击安装字体文件即可。注意，虽然macOS内置了Times New Roman字体，但是该内置字体版本过于老旧，有缺字的现象，建议将7个字体文件全部安装。

然后就可以根据[编译](#编译)里的方法去编译了。

### Overleaf

在[Overleaf in Chinese](https://cn.overleaf.com/)平台使用时，由于Overleaf是安装在GNU/Linux上的最新版的TeX Live，用户无需考虑LaTeX套装版本问题，仅需要安装字体即可，用户首先将本仓库[下载](https://github.com/note286/xdupgtp/archive/refs/heads/main.zip)，再根据[GNU/Linux](#gnulinux)中的方法得到字体文件。

在Overleaf左上角点击创建新项目，选择上传项目，将压缩包上传至Overleaf，会自动进入该论文模板项目。点击左上角新建目录按钮，新建一个名为`fonts`的文件夹，选中`fonts`文件夹，点击左上角上传按钮将所有的字体文件上传。最后根据[Overleaf编译](#overleaf编译)配置如何在线编译。

### TeXPage

在[TeXPage](https://www.texpage.com/)平台使用时，由于TeXPage是安装在GNU/Linux上的最新版的TeX Live，用户无需考虑LaTeX套装版本问题，仅需要安装字体即可，用户首先将本仓库[下载](https://github.com/note286/xdupgtp/archive/refs/heads/main.zip)，再根据[GNU/Linux](#gnulinux)中的方法得到字体文件。

在TeXPage[个人主页](https://www.texpage.com/console)左上角点击创建，选择上传项目，将压缩包上传至TeXPage，进入该论文模板项目。点击左上角新建文件夹按钮，新建一个名为`fonts`的文件夹，选中`fonts`文件夹，点击左上角上传文件按钮将所有的字体文件上传。最后根据[TeXPage编译](#texpage编译)配置如何在线编译。

## 学位类型

本项目模板支持学术学位博士研究生、专业学位博士研究生、学术学位硕士研究生和专业学位硕士研究生共4种类型开题报告表，相应的文档类可选参数如下：

- `da`，学术学位博士研究生（Doctor of Academic）
- `dp`，专业学位博士研究生（Doctor of Professional）
- `ma`，学术学位硕士研究生（Master of Academic）
- `mp`，专业学位硕士研究生（Master of Professional）

例如，切换为专业学位博士研究生，即将

```latex
\documentclass{xdupgtp}
```

改为

```latex
\documentclass[dp]{xdupgtp}
```

默认为学术学位博士研究生，即不添加文档类可选参数则为学术学位博士研究生。

此外，在`examples`中已内置对应学位类型的`.tex`文件，用户可以将`xdupgtp.tex`中所有文件内容替换为相应的`xdupgtp-*.tex`文件内容，避免手动配置的麻烦。

## 编译

本项目目前仅在Windows和GNU/Linux平台上的TeX Live 2021和macOS平台上的MacTeX 2021进行了测试，均更新所有包至最新版，并参考[字体安装](#字体安装)安装了缺失字体。命令编译时切换到`xdupgtp.tex`所在目录执行命令即可。IDE编译选择对应IDE中的`XeLaTeX`的编译方式，参考文献使用`BibTeX`编译。关于PDF查看器，Windows平台上推荐使用[Sumatra PDF Viewer](https://www.sumatrapdfreader.org/free-pdf-reader)，macOS平台上推荐[Skim](https://skim-app.sourceforge.io/)，适当配置可支持正向同步和反向同步。

### 命令编译

介绍如何使用命令编译，可选择使用`latexmk`来快速编译或者常规的四次编译。

#### latexmk编译

编译

```shell
latexmk
```

清理辅助文件

```shell
latexmk -c
```

#### 四次编译

编译

```shell
xelatex -synctex=1 xdupgtp
bibtex xdupgtp
xelatex -synctex=1 xdupgtp
xelatex -synctex=1 xdupgtp
```

清理辅助文件

```shell
latexmk -c
```

### 文本编辑器编译

任何一款[文本编辑器](https://zh.wikipedia.org/wiki/%E6%96%87%E6%9C%AC%E7%BC%96%E8%BE%91%E5%99%A8)均可以编辑`.tex`文件，包括[Sublime Text](https://www.sublimetext.com/)和[Visual Studio Code](https://code.visualstudio.com/)等，大部分文本编辑器均提供自定义编译功能，例如Sublime Text的[Build Systems](https://www.sublimetext.com/docs/build_systems.html)，可以参考[命令编译](#命令编译)自行创建相应的编译配置，利用编译快捷键进行编译。此外，一些文本编辑器支持安装扩展，例如Sublime Text可以安装[LaTeXTools](https://packagecontrol.io/packages/LaTeXTools)来辅助进行`.tex`文件的编辑，还提供了一些常用的编译配置。可以搭配Sumatra PDF Viewer或Skim实现反向同步，正向同步一般需要文本编辑器或其扩展支持。

一些文本编辑器不支持自定义编译功能或者安装扩展，依然可以使用文本编辑器来编辑`.tex`文件，使用命令来进行编译。

### WinEdt编译

下载[WinEdt](https://www.winedt.com/download.html)安装包并安装，支持Windows平台。安装后可以查看[Quick Guide](http://www.winedt.com/download.html#Quick_Guide)获取更多关于WinEdt的使用帮助。

打开WinEdt后，点击File->Open打开`xdupgtp.tex`文件。点击Option->Execution Modes，在弹出的面板左侧选择TeXify，在面板左下角点击Browse for executable，依次找到`C:\texlive\2021\bin\win32\latexmk.exe`文件并点击打开，如果安装TeX Live至非默认目录，依情况修改；将左下角的Switches中对应值清空，最后点击面板上的OK。

在Toolbar中PDF Preview左侧的按钮下拉菜单中可以切换编译引擎。完全编译选择TeXify，可以自动处理交叉引用和参考文献引用，编译时间较长；不考虑交叉引用和参考文献引用时，快速编译选择XeLaTeX，编译时间较短，需要参考文献引用时再点击TeX->BibTeX编译参考文献，接着执行两次XeLaTeX编译可以生成参考文献列表和参考文献引用。

点击Tools->Erase Output Files或者Toolbar中的Erase Output Files按钮，在弹出的面板中再点击Delete Now可以清理辅助文件，常用于某次报错后清理错误的辅助文件，避免二次报错。

可以参考[QuickGuide.pdf](http://www.winedt.com/doc/QuickGuide.pdf)中第2.3节配置WinEdt默认PDF查看器为Sumatra PDF Viewer，即点击Option->Execution Modes，在弹出的面板选择PDF Viewer标签，将PDF Viewer Executable改为SumatraPDF.exe，Sumatra PDF Viewer默认安装在`%LOCALAPPDATA%\SumatraPDF\`处，这样就可以使用Sumatra PDF Viewer来查看PDF文件。Sumatra PDF Viewer的反向同步一般WinEdt会自动配置，如果需要手动配置，在Sumatra PDF Viewer左上角点击三道杠->设置->选项，在最后设置反向搜索命令行中填写

```
"C:\Program Files\WinEdt Team\WinEdt 10\WinEdt.exe" "[Open(|%f|);SelPar(%l,8);]"
```

并点击确定即可。

注意，由于WinEdt添加新的编译配置较为复杂，本方法将TeXify内的编译引擎由LaTeX改为latexmk，并使用了主目录下的`latexmkrc`编译配置。

### TeXworks编译

下载[TeXworks](https://tug.org/texworks/)安装包并安装，支持Windows，GNU/Linux和macOS平台。安装后可以查看[A short manual for TeXworks](https://github.com/TeXworks/manual/releases)获取更多关于TeXworks的使用帮助。

打开TeXworks后，点击编辑->首选项->排版->处理工具，点击右下角蓝色加号，在弹出的面板中名称处填写latexmk，程序处点击右侧浏览选择`C:\texlive\2021\bin\win32\latexmk.exe`文件并点击打开，如果安装TeX Live至非默认目录，依情况修改，最后点击面板上的OK。选择新建的latexmk，点击右侧的蓝色上箭头移动至顶部，再将内置的XeLaTeX和BibTeX移动至顶部，使得latexmk、XeLaTeX和BibTeX位于处理工具的顶部，方便后续切换引擎。再选择下方的默认，可以将latexmk或者XeLaTeX设置为默认，最后点击OK。

点击文件->打开，选择`xdupgtp.tex`文件，Toolbars左上角可以切换编译引擎。完全编译选择latexmk，可以自动处理交叉引用和参考文献引用，编译时间较长；不考虑交叉引用和参考文献引用时，快速编译选择XeLaTeX，编译时间较短，需要参考文献引用时切换至BibTeX编译参考文献，接着执行两次XeLaTeX编译可以生成参考文献列表和参考文献引用。

点击文件->删除辅助文件，在弹出的面板中再点击删除可以清理辅助文件，常用于某次报错后清理错误的辅助文件，避免二次报错。

TeXworks内置了PDF查看器，支持正向同步和反向同步功能，具体请查看[A short manual for TeXworks](https://github.com/TeXworks/manual/releases)中5.1节。

### TeXstudio编译

下载[TeXstudio](https://www.texstudio.org/#download)安装包并安装，支持Windows，GNU/Linux和macOS平台。安装后可以查看[TeXstudio : User manual](https://htmlpreview.github.io/?https://github.com/texstudio-org/texstudio/master/utilities/manual/usermanual_en.html)获取更多关于TeXstudio的使用帮助。

打开TeXstudio后，点击文件->打开，选择`xdupgtp.tex`文件。点击选项->设置TeXstudio->命令，将Latexmk处值改为`latexmk.exe`，切换至构建标签，将默认编译器改为Latexmk或者XeLaTeX。

TeXstudio无法快速切换编译引擎，只能在选项->设置TeXstudio->构建里修改默认编译器，或者点击工具->命令里临时运行指定的编译引擎。完全编译选择latexmk，可以自动处理交叉引用和参考文献引用，编译时间较长；不考虑交叉引用和参考文献引用时，快速编译选择XeLaTeX，编译时间较短，需要参考文献引用时切换至BibTeX编译参考文献，接着执行两次XeLaTeX编译可以生成参考文献列表和参考文献引用。

点击工具->清理辅助文件，在弹出的面板中选择合适的范围再点击OK便可以清理辅助文件，常用于某次报错后清理错误的辅助文件，避免二次报错。

TeXstudio内置了PDF查看器，支持正向同步和反向同步功能，具体请查看[TeXstudio : User manual](https://htmlpreview.github.io/?https://github.com/texstudio-org/texstudio/master/utilities/manual/usermanual_en.html)中4.10节。

### Texmaker编译

下载[Texmaker](https://www.xm1math.net/texmaker/)安装包并安装，支持Windows，GNU/Linux和macOS平台。安装后可以查看[Texmaker : User manual](https://www.xm1math.net/texmaker/doc.html)获取更多关于Texmaker的使用帮助。

打开Texmaker后，点击文件->打开，选择`xdupgtp.tex`文件。点击选项->配置Texmaker->命令，将LaTeX-Mk中对应值改为`latexmk`，点击OK。

工具栏中可以切换编译引擎。完全编译选择latexmk，可以自动处理交叉引用和参考文献引用，编译时间较长；不考虑交叉引用和参考文献引用时，快速编译选择XeLaTeX，编译时间较短，需要参考文献引用时切换至BibTeX编译参考文献，接着执行两次XeLaTeX编译可以生成参考文献列表和参考文献引用。

点击工具->清除历史记录，在弹出的面板中再点击删除文件可以清理辅助文件，常用于某次报错后清理错误的辅助文件，避免二次报错。

Texmaker内置了PDF查看器，支持正向同步和反向同步功能，具体请查看[Texmaker : User manual](https://www.xm1math.net/texmaker/doc.html)中3.3节。

### Overleaf编译

用户首先根据[Overleaf](#overleaf)中关于字体安装的介绍安装好字体，再点击左上角的菜单按钮修改编译器为`XeLaTeX`，最后为`xdupgtp`文档类传入`overleaf`参数，即将`xdupgtp.tex`中

```latex
\documentclass{xdupgtp}
```

改为

```latex
\documentclass[overleaf]{xdupgtp}
```

后即可正常编译。

### TeXPage编译

用户首先根据[TeXPage](#texpage)中关于字体安装的介绍安装好字体，再点击右上角的设置按钮修改LaTeX编译器为`XeLaTeX`，最后为`xdupgtp`文档类传入`texpage`参数，即将`xdupgtp.tex`中

```latex
\documentclass{xdupgtp}
```

改为

```latex
\documentclass[texpage]{xdupgtp}
```

后即可正常编译。

## 参考文献引用

在开题报告表中，一般仅国内外研究现状处会出现参考文献引用，因此用户在撰写国内外研究现状时可以直接引用参考文献，对应的参考文献列表会自动出现在国内外研究现状后，无需用户干预，例如：

```latex
测试引用\cite{ChangHTD19,WangZSS21,GongL21}是否正常。
```

已添加部分常用类型参考文献条目样例至`xdupgtp.bib`，用户可以参考使用，需要注意的是，不要轻易使用分组即`{}`，尤其是`author`字段。参考文献样式符合已于2015年12月1日实施的国家标准《信息与文献 参考文献着录规则》（标准号[GB/T 7714-2015](http://std.samr.gov.cn/gb/search/gbDetailed?id=71F772D8055ED3A7E05397BE0A0AB82A)），用户可以自行下载相应标准查看示例。用户可以使用[dblp](https://dblp.org/)生成的bib条目，[百度学术](https://xueshu.baidu.com/)和[Google Scholar](https://scholar.google.com.hk/)导出的bib文件不是很规范，经常有很大问题，感兴趣的可以去[BibTeX format explained](https://www.bibtex.com/g/bibtex-format/)了解bib文件的合法格式，遇到[dblp](https://dblp.org/)没有的条目，可以手动整理。

在[btxdoc](https://mirrors.ustc.edu.cn/CTAN/biblio/bibtex/base/btxdoc.pdf)文档中第3.1章节指出：

> `article`: An article from a journal or magazine. **Required fields**: author, title, journal, year. **Optional fields**: volume, number, pages, month, note.
>
> `book`: A book with an explicit publisher. **Required fields**: author or editor, title, publisher, year. **Optional fields**: volume or number, series, address, edition, month, note.
>
> `booklet`: A work that is printed and bound, but without a named publisher or sponsoring institution. Required field: title. **Optional fields**: author, howpublished, address, month, year, note.
>
> `conference`: The same as INPROCEEDINGS, included for Scribe compatibility.
>
> `inbook`: A part of a book, which may be a chapter (or section or whatever) and/or a range of pages. **Required fields**: author or editor, title, chapter and/or pages, publisher, year. **Optional fields**: volume or number, series, type, address, edition, month, note.
>
> `incollection`: A part of a book having its own title. **Required fields**: author, title, booktitle, publisher, year. **Optional fields**: editor, volume or number, series, type, chapter, pages, address, edition, month, note.
>
> `inproceedings`: An article in a conference proceedings. **Required fields**: author, title, booktitle, year. **Optional fields**: editor, volume or number, series, pages, address, month, organization, publisher, note.
>
> `manual`: Technical documentation. Required field: title. **Optional fields**: author, organization, address, edition, month, year, note.
>
> `mastersthesis`: A Master’s thesis. **Required fields**: author, title, school, year. **Optional fields**: type, address, month, note.
>
> `misc`: Use this type when nothing else fits. **Required fields**: none. **Optional fields**: author, title, howpublished, month, year, note.
>
> `phdthesis`: A PhD thesis. **Required fields**: author, title, school, year. **Optional fields**: type, address, month, note.
>
> `proceedings`: The proceedings of a conference. **Required fields**: title, year. **Optional fields**: editor, volume or number, series, address, month, organization, publisher, note.
>
> `techreport`: A report published by a school or other institution, usually numbered within a series. **Required fields**: author, title, institution, year. **Optional fields**: type, number, address, month, note.
>
> `unpublished`: A document having an author and title, but not formally published. **Required fields**: author, title, note. **Optional fields**: month, year.

在示例文件中已经提供了若干个条目供参考。需要注意的是，无论中英文，每个作者均使用`and`连接。除非文献卷号、期号和页码均无，否则不必提供DOI选项。对于网页链接，使用`misc`类型条目，填写`author`、`title`、`howpublished`和`year`选项即可。

# 版本记录

- `2022-01-02` [`v0.6.0`](https://github.com/note286/xdupgtp/releases/tag/v0.6.0) 新增支持Overleaf和TeXPage。
- `2022-01-01` [`v0.5.1`](https://github.com/note286/xdupgtp/releases/tag/v0.5.1) 修复开题报告评语及结论中脚注不显示的bug。
- `2022-01-01` [`v0.5.0`](https://github.com/note286/xdupgtp/releases/tag/v0.5.0) 支持自动添加PDF元数据。
- `2022-01-01` [`v0.4.1`](https://github.com/note286/xdupgtp/releases/tag/v0.4.1) 配置\subsubsection{}样式。
- `2022-01-01` [`v0.4.0`](https://github.com/note286/xdupgtp/releases/tag/v0.4.0) 支持国内外研究现状引用参考文献。
- `2022-01-01` [`v0.3.0`](https://github.com/note286/xdupgtp/releases/tag/v0.3.0) 新增专业学位硕士研究生模板。
- `2022-01-01` [`v0.2.2`](https://github.com/note286/xdupgtp/releases/tag/v0.2.2) 修改选题来源填写位置。
- `2021-12-31` [`v0.2.1`](https://github.com/note286/xdupgtp/releases/tag/v0.2.1) 增加不同学位类型示例文件。
- `2021-12-31` [`v0.2.0`](https://github.com/note286/xdupgtp/releases/tag/v0.2.0) 新增学术学位硕士研究生模板。
- `2021-12-31` [`v0.1.0`](https://github.com/note286/xdupgtp/releases/tag/v0.1.0) 新增专业学位博士研究生模板。
- `2021-12-31` [`v0.0.1`](https://github.com/note286/xdupgtp/releases/tag/v0.0.1) 新增学术学位博士研究生模板。

# 免责声明

本模板的发布遵守[LaTeX Project Public License 1.3c](http://www.latex-project.org/lppl.txt)以及其后的最新版本，使用前请认真阅读协议内容。

本模板为作者个人制作，使用仅供参考，任何由于使用本模板而引起的任何问题均与本模板作者无关。

任何个人或组织以本模板为基础进行修改、扩展而生成的新的专用模板，请严格遵守[LaTeX Project Public License 1.3c](http://www.latex-project.org/lppl.txt)协议以及其后的最新版本。由于违犯协议而引起的任何纠纷争端均与本模板作者无关。

# 作者

- [@note286](https://github.com/note286)
