# Git-Usage

## 新建repo
1. 登陆github，选择New repository，勾选readme.md
* 使用`git clone`命令将仓库克隆到本地
* 通过`git checkout master`选择master分支进行修改（若要修改gh-pages分支则使用`git checkout gh-pages`命令切换到gh-pages分支进行修改）
* 修改完后添加需要提交的部分，如果仓库不是很大，可以使用`git add .`命令提交所有
* 使用`git commit -m '提交说明'`命令添加本次提交的注释
* 使用`git push origin master`命令将修改的master分支提交到远程仓库（`git push origin gh-pages`命令将修改的gh-pages分支提交到远程仓库）