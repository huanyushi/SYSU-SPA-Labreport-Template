<div align='center'>

# SYSU-SPA-Labreport-Template

<b>中山大学物理与天文学院本科实验报告LaTeX模板</b> 

<b><a href='README_EN.md'>English version</a></b> 

![GitHub license](https://img.shields.io/github/license/huanyushi/SYSU-SPA-labreport-Template.svg) ![Github Version](https://img.shields.io/github/release/huanyushi/SYSU-SPA-labreport-Template.svg)
<p align = "center">
<img src="images/example.png" width="20%" />
</p>
</div>

大家好，我是来自于物理与天文学院2019级物理系的本科生 Huanyu Shi。

本模板源于我大二一时兴起所做。对于撰写实验报告，学院只提供了简陋的 word 模板，使用 word 效率低下且排版效果不甚理想。于是我仿照学院提供的模板格式，在其基础上完成了此 LaTeX 模板。

临近毕业，我发现此模板在学院内部仍有流传，但毕竟当时写就并不规范，且功能有诸多缺失。考虑到种种原因，**我决定将此模板进行更新完善并打包公布在 GitHub 和知乎上**，希望有助于后辈学子，同时也希望对其他兄弟院校的同学有一定参考和帮助作用。
	
Demo 请见 [PDF](https://huanyushi.github.io/assets/pdf/SYSU-SPA-LabReport-Template.pdf) ，源码可在 [release](https://github.com/huanyushi/SYSU-SPA-Labreport-Template/releases) 上下载。


同时，也欢迎访问我的 [blog](https://huanyushi.github.io/)

## 模板功能说明

### 更新内容
本模板经过本次更新后，除几个必要的实验报告部分：
* 扉页
* 预习报告
* 实验记录
* 分析与讨论

在此前的实验报告基础上我增加了以下几个内容：
* **参考文献**，注明引用内容是是作者对他人知识成果的承认和尊重，是保证学术诚信必须养成的习惯；

* **代码附录**，给出了使用 Lstlisting 环境展示代码的示例；

* **常用命令展示**，鉴于部分学生初次接触 LaTeX，本模板也给出了相应的常用命令展示以方便查阅。

### 注意事项
1. 参考文献应导入 `bib` 文件中，编译顺序请按 `xelatex` -> `bibtex` -> `xelatex` -> `xelatex`， 若要调整参考文献的格式在 `main.tex` 中修改 `\bibliographystyle{}` 即可；
2. `lstlisting` 代码环境配置如下，导入的是 `Python` 语言，可手动更改或添加其他程序语言，其他相关配置可参考 `listings` 宏包的手册，
```latex
\usepackage{listings}
\definecolor{c1}{HTML}{2752C9} % 定义的颜色
\lstloadlanguages{python}
\lstdefinestyle{pythonstyle}{
backgroundcolor=\color{gray!5},
language=python,
frameround=tftt,
frame=shadowbox, 
keepspaces=true,
breaklines,
columns=spaceflexible,                   
basicstyle=\ttfamily\small, % 基本文本设置，字体为 teletype，大小为 small
keywordstyle=[1]\color{c1}\bfseries, 
keywordstyle=[2]\color{Red!70!black},   
stringstyle=\color{Purple},       
showstringspaces=false,
commentstyle=\ttfamily\scriptsize\color{green!40!black}, % 注释文本设置，字体为 teletype，大小为 scriptsize
tabsize=2,
morekeywords={as},
morekeywords=[2]{np, plt, sp},
numbers=left, % 代码行数，位置在左
numberstyle=\it\tiny\color{gray}, % 代码行数的数字字体设置
stepnumber=1,
rulesepcolor=\color{gray!30!white}
}
```
![](images/readme1.jpg)
3. 本模板定义了两种形式的 `box` ，可参考 `tcolorbox` 宏包的手册进行修改，
```latex
\usepackage{tcolorbox}
\tcbuselibrary{skins,breakable}
\newtcolorbox{tbox}[2][]{
    colframe=black!70!,
    breakable,
    enhanced,
	boxrule =0.5pt,
    title = {#2},
    fonttitle = \large\bfseries,
	drop fuzzy shadow,
    #1
}
\newtcolorbox[auto counter,number within=section]{question}[1][]{
  top=2pt,bottom=2pt,arc=1mm,
  boxrule=0.5pt,
  breakable,
  enhanced, % 跨页后不会显示下边框
  coltitle=c1!80!gray,
  colframe=c1,
  colback=c1!3!white,
  drop fuzzy shadow,
  title={思考题~\thetcbcounter：\quad},
  fonttitle=\bfseries,
  attach title to upper,
  #1
}
```
![](images/readme2.jpg)
4. TikZ 是一个知名的绘图宏包（其文档说明高达1000多页，超乎常人想象），在此补充了一些 TikZ 实例
![](images/readme3.JPG)

## 声明
* 本模板仅供学习交流所用，非学院官方模板。
* 本模板不再进行更新维护，若有任何额外需求请自行设计更改。
* **欢迎报考中山大学物理与天文学院**。

## 许可证
该项目是在 MIT 许可下发布的。