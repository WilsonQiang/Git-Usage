# Git-Usage

## 新建repo
1. 登陆github，选择New repository，勾选readme.md
2. 使用`git clone`命令将仓库克隆到本地，使用`cd`命令进入仓库，使用`ls -a`查看，发现本地已经新建`.git`文件
3. 通过`git checkout master`选择master分支进行修改（若要修改gh-pages分支则使用`git checkout gh-pages`命令切换到gh-pages分支进行修改）
4. 修改完后添加需要提交的部分，如果仓库不是很大，可以使用`git add .`命令提交所有
5. 使用`git commit -m '提交说明'`命令添加本次提交的注释
6. 使用`git push origin master`命令将修改的master分支提交到远程仓库（`git push origin gh-pages`命令将修改的gh-pages分支提交到远程仓库）

## 从本地新建仓库后上传到github（gitbook的上传方法）
1. 在本地新建一个文件夹例如egbook，使用命令`gitbook init egbook`新建一个egbook文件夹并在其中初始化书籍目录并写入README.md 和 SUMMARY.md两个文件，README.md 是对书籍的简单介绍, SUMMARY.md 是书籍的目录结构
2. 进入egbook文件夹，使用`gitbook serve`命令编译书籍（调用gitbook build命令）并打开web服务器，监听在本地的 4000 端口,生成_book文件夹，_book文件夹中的文件为编译后可通过web服务器之间访问的网页文件
3. 本地编辑gitbook书籍后等待提交到远程仓库
4. 在远程仓库New repository，命名为egbook，不勾选生成readme.md文件
5. 本地cd进入egbook文件夹，使用`git init`命令初始化egbook文件夹，生成`.git`文件
6. 使用仓库中的提示`…or push an existing repository from the command line`中的命令`git remote add origin https://github.com/WilsonQiang/egbook.git`关联远程仓库
7. 使用`git add .`提交全部修改
8. 使用`git commit -m '第一次提交egbook'`为本次提交添加注释
9. 使用仓库中的提示`…or push an existing repository from the command line`中的命令`git push -u origin master`提交第一次修改
10. 下面需要新建gh-pages分支用来生成可访问的独立网址（master分支用来保存源码，gh-pages分支用来保存书籍编译后的 HTML 文件）
11. 在新建gh-pages分支之前先将_book文件夹(用来保存书籍编译后的 HTML 文件)备份
12. 使用`git checkout -b gh-pages`命令新建gh-pages分支（同时switch到gh-pages分支）
13. 然后删除egbook文件夹中的所有文件，再讲_book文件夹中的所有文件复制到egbook中
14. 使用`git add .`提交全部修改
15. 使用`git commit -m '第一次提交gh-pages分支'`为本次提交添加注释
16. 使用`git push origin gh-pages`命令将本次修改提交到远程仓库
17. 在远程仓库的gh-pages分支的setting中可以找到egbook这本gitbook的网页链接https://wilsonqiang.github.io/egbook/
18. 在本地终端中通过`git checkout master`再次切换回master分支（注意看egbook文件夹的变化），也可以通过`git checkout gh-pages`切换到gh-pages分支（注意egbook文件夹变化）