
### 一、生成SSH KEY

打开命令终端CMD，或者git bash；输入命令
ssh-keygen -t rsa -C "user1@email.com"
回车，生成user1的id_rsa私钥和id_rsa_pub公钥；
生成时可直接修改钥匙的名称，
否则，欲采用多帐户配置，
需手动修改默认生成的“id_rsa和id_rsa_pub”名称，以避免生成另外的帐户钥匙。

### 二、编辑SSH配置文件

打开或创建~/.ssh/config，“~”代表系统盘下.ssh文件夹前面的路径。编辑config文件：
```# user1 的说明
Host user1 #此处User1可以是自由命名。
HostName github.com #多用户主机相同，如均为github,则名称不变
User git #如果采用的是同一个主机，如github，此行似乎可省。
IdentityFile ~/.ssh/id_rsa_user1 #ssh key的路径和名称

# user2 的说明
Host user2
HostName github.com
IdentityFile ~/.ssh/id_rsa_user2

# User3 依上类推。
```
### 三、添加私钥至ssh-agent缓存
输入命令
```
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/user1_id_rsa #user1_id_rsa为前面所命名的ssh key名称。
$ ssh-add ~/.ssh/user2_id_rsa
# 可继续添加其它私钥
$ ssh-add ~/.ssh/userx_id_rsa
```
### 四、在Github（或Gitlib）中添加SSH Key


### 五、使用main帐户添加远程仓库

