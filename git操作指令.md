# git操作指令

## 仓库的创建与操作

**`git -v`** 查看版本号

![image-20231206165414558](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206165414558.png)

**初始化仓库的过程**

**`git init`**  在当前路径下创建仓库

![image-20231206165438014](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206165438014.png)

HEAD文件表示引用，指向我们的分支，指向master分支，master是命令行默认创建的分支

refs指向提交记录 最后一次提交版本号

**从远程仓库下载到本地**

`git clone` **远程仓库地址 （自定义名称可加可不加）下载远程仓库到本地**

对远程仓库进行操作要进行配置用户名和邮箱在当前文件夹下下载的仓库进行配置

`**git config user.name**` 配置的名称

`git config user.email` 配置的邮箱地址

也可以不通过命令行修改config

**添加全局配置** 

`git config --global user.name`

`git config --global user.email`

## git命令文件操作



**git status**  表示状态，查看暂存区的状态

![image-20231206165519122](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206165519122.png)

![image-20231206164006732](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206164006732.png)

**git add**文件名 添加文件到暂存区进行操作比对，来判断文件的变化

![image-20231206165547181](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206165547181.png)

**git rm --cached 文件名**将文件从暂存区删除

![image-20231206165613073](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206165613073.png)

***通配符**

**git commit -m 注释文件名  将文件提交到仓库**

![image-20231206165645884](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206165645884.png)

**git log 查看提交记录**

![image-20231206165736714](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206165736714.png)

**git log --oneline** **用一行来显示提交记录**

**![image-20231206170008314](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206170008314.png)**

**删除文件后的操作**

git status 查看文件状态

git add b.txt 将文件添加到暂存区

git commit -m 删除文件 -》提交文件的操作记录

![image-20231206170321865](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206170321865.png)

### 文件被误删除操作

**git restore 文件名 将误删除的文件恢复**

![image-20231206171215027](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206171215027.png)

如果提交了删除操作，也可以通过之前的版本将其恢复

**git reset --hard 版本号**

![image-20231206171735645](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206171735645.png)

历史记录也将重置到开始的提交记录，会将我们的提交过程丢失。所以可以使用下面的指令

git revert 版本号（还原，将我们的仓库恢复到这个版本号之前的提交） （恢复到上一个版本，需要找到他的下一个提交版本号）

![image-20231206172447783](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231206172447783.png)

## git命令-分支操作

**git branch 分支名**    **创建分支操作**

**git branch 创建分支基于提交操作**

![image-20231207082945533](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207082945533.png)

**git branch -v 查看有多少分支**

![image-20231207083025378](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207083025378.png)

**git checkout 分支名** **切换分支操作**

![image-20231207083247102](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207083247102.png)

**由master切换到user**

**创建分支操作可以和切换分支操作合并成一步**

**git checkout -b 分支名**

![image-20231207083559706](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207083559706.png)

**git branch -d 分支名 删除分支操作**

![image-20231207083801874](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207083801874.png)

### git命令-分支操作-合并和冲突

**如果想要将两个分支合并在一起，首先要切换到主分支（master）,然后将次分支合并到master分支**

**git merge order（合并分支名）**  **合并操作**

![image-20231207085148778](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207085148778.png)

**如果两个文件冲突****需要比对两个文件，由我们自己操作文件，然后重新提交文件**

![image-20231207085217470](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207085217470.png)

## git标签指令

创建标签指令

**git tag**   查看标签

**git tag 标签名 版本号**

![image-20231207090419897](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207090419897.png)

**git log 标签名** 查看标签以及之前的版本记录

![image-20231207090525925](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207090525925.png)

**可以给每个版本增加标签但是标签不能重复**

**git tag -d uptfile（标签名）** 删除标签操作

![image-20231207090757975](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207090757975.png)

**标签还可以用来创建分支（创建的分支名称就是我们的标签名称），分支就是引用了一个提交的版本号，而标签就是给版本号增加了一个别名**

**git checkout -b addfile(标签名)**

![image-20231207091230701](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207091230701.png)

## git 远程仓库的操作

**git remote add origin增加**

**git remote remove origin删除**

**git remote rename origin改名称**

**将本地仓库的数据提交到远程仓库**

**git push origin**   **将数据推送到远程操控指令**

![image-20231207092504027](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207092504027.png)

**使用ssh地址推送到远程仓库，需要提交安全认证功能，需要生成一个安全证书**

**ssh-keygen -t rsa -C(ssh地址**)

![image-20231207092756732](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207092756732.png)

**生成之后需要将ssh证书，找到安全认证文件夹提交到远程仓库的设置里**

![image-20231207093108790](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207093108790.png)

![image-20231207093128096](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207093128096.png)

![image-20231207093146863](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207093146863.png)

![image-20231207093220591](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207093220591.png)

**然后重新执行就可以**

**远程仓库更新之后，通过拉取操作让本地仓库也更新**

**git pull origin(远程地址名称)**

![image-20231207093459167](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207093459167.png)

# gitlab 搭建自己的代码托管平台

需要运行在Linux操作系统上

**第一步安装**

![image-20231207093844426](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207093844426.png)

此安装路径需要自行修改

**第二步安装配置依赖项**

![image-20231207094027935](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094027935.png)

**第三步初始化gitlab**

![image-20231207094131539](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094131539.png)

安装步骤需要改成自己的虚拟机主机地址

第四步启动gitlab

![image-20231207094356568](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094356568.png)

第五步访问gitlab

![image-20231207094430975](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094430975.png)

需要改成自己的虚拟机主机名称

![image-20231207094510060](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094510060.png)

登陆

![image-20231207094805761](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094805761.png)

![image-20231207094850301](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094850301.png)

![image-20231207094910915](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094910915.png)

![image-20231207094938301](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207094938301.png)

![image-20231207095024612](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095024612.png)

![image-20231207095114343](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095114343.png)

![image-20231207095135451](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095135451.png)

![image-20231207095206466](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095423828.png)

![image-20231207095227556](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095227556.png)

![image-20231207095338955](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095338955.png)

**配置远程库**

![image-20231207095313763](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095313763.png)

![image-20231207095544533](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095544533.png)

**url***地址需要改成虚拟机的地址**

![image-20231207095700630](C:\Users\刘倩\AppData\Roaming\Typora\typora-user-images\image-20231207095700630.png)

**当远程仓库改变时，与远程仓库同步功能使用pull**