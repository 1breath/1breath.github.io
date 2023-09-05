
### 第一步，安装hugo
#### windows
1. 用choco 命令安装：以管理员身份运行对话终端，输入命令：choco install hugo；如果之前安装过，可以用 choco uninstall hugo命令卸载，然后，再安装。
3. 

### 第二步，hugo命令建立一个本地站点（文件夹）


### 第三步，hugo new 命令创建博文


## 第二部分 安装主题

### 第一步，下载主题，
### 第二步， 解压缩至hugo命令所建本地站点文件夹的theme文件夹里 
### 第三步，修改config.yuml文件

## 第三部分 推送至github.
配置一下博客的 config 文件, 注意 `themesDir = "themes"` 不要添加斜杠 `/`, 否则在下一步利用 GitHub Action自动部署会报找不到主题的错误.

hugo -D 
hugo 
cd ./public 
git add -A 
git commit -m "脚本提交" 
git push -u origin main
### 在github修改master为main后，提示
git branch -m master main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a

