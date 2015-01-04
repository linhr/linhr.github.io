---
layout: post
title: "Ubuntu下THUThesis配置过程"
date: 2014-05-26 10:41:56+0800
categories: blog
---


拖到第14周周一，终于要动笔写毕业论文了。使用LaTeX撰写论文自然离不开强大的THUThesis模板。项目地址在这里：<https://github.com/xueruini/thuthesis>。

下面简要记录一下在Ubuntu下折腾THUThesis遇到的坑。

我使用的Ubuntu版本为12.04 LTS。由于Ubuntu软件仓库中的TeX Live版本比较陈旧，因此很久很久以前我是使用PPA方式安装的。安装命令貌似如下所示。

```bash
sudo add-apt-repository ppa:texlive-backports/ppa
sudo apt-get install texlive texlive-xetex texlive-latex-extra texlive-science texlive-bibtex-extra
```

直接编译THUThesis会遇到一系列错误。下面是解决方案。

1. 	安装TeX Live及CTeX宏包

	THUThesis使用[CTeX](http://ctan.org/pkg/ctex)宏包处理中文。我一直以来使用`xelatex`编译.tex文件，使用xeCJK处理中文，因此CTeX包未安装。使用`apt-get`方式（而不是ISO镜像方式）安装的TeX Live不能使用`tlmgr`工具管理宏包，因此CTeX只能手动安装。

	运行以下命令查看TeX Live查找宏包的路径。

	```bash
	kpsepath tex | sed -e 's/:/\n/g'
	```

	可以将CTeX安装到用户目录下。

	```bash
	mkdir -p ~/texmf/tex/latex
	cd ~/texmf/tex/latex
	wget http://mirrors.ctan.org/language/chinese/ctex.zip
	unzip ctex.zip
	rm ctex.zip
	```

2. 	安装中英文字体

	论文中使用的中英文字体可以从Windows下复制（只需双击打开字体文件并安装即可）。Times New Roman、Arial和Courier New三款英文字体也可使用下列命令安装。

	```bash
	sudo apt-get install msttcorefonts
	```

	使用下列命令刷新字体缓存。

	```bash
	sudo fc-cache -f -v
	```

	使用`fc-list`命令可以查看已安装的字体列表。

3. 	我在编译THUThesis时提示`fig2dev`命令未找到。使用下列命令安装该工具。
	
	```bash
	sudo apt-get install fig2ps
	```

	此外，如需使用`convert`工具应使用下列命令安装。

	```bash
	sudo apt-get install imagemagick
	```

4. 	至此，可以尝试运行`make`编译THUThesis了。需要注意的时，编译书脊时需要将shuji.tex中的

	```latex
	\documentclass[doctor]{thuthesis}
	```

	改为

	```latex
	\documentclass[doctor,nofonts]{thuthesis}
	```

	否则由于CTeX的缺陷编译时将提示SIMKAI.TTF字体未找到等错误。其它具体配置参见main.tex头部的说明。
