###     最近一直觉得自己工作效率很差，有些浑浑噩噩的感觉。可能是对自己的要求有些松懈。**为了整理近期工作中思路，给自己一些鞭策，决定重新开始撰写工作和学习笔记。做这件事情之前，首先要建立属于自己的网站。**查了一些资料，推荐使用[blogdown](https://bookdown.org/yihui/blogdown/)作为入门工具。

#### 1. 创建Github库，复制库链接

<img src="https://github.com/wangdata/imageshare/blob/main//img/202204271945851.png?raw=true>



#### 2. 在RStudio中创建git工作目录

##### 2.1 下载Git，配置

[Git - Downloads (git-scm.com)](https://links.jianshu.com/go?to=https%3A%2F%2Fgit-scm.com%2Fdownload): 

```
配置Git
win 系统打开 CMD或者Git Bash，代码如下：

git config --global user.name "你GitHub的名字"
例如：git config --global user.name "Jane Doe"

git config --global user.email 你GitHub的注册邮箱
例如：comgit config --global user.email janedoe@gmail.com

#检查配置是否成功
git config ––list
```

![](https://github.com/wangdata/imageshare/blob/main//img/202204272002767.png?raw=true)

##### 2.2 File--New Project--Version Control--Git

![image-20220427194722968](https://github.com/wangdata/imageshare/blob/main//img/202204271947052.png?raw=true)



![image-20220427194812884](https://github.com/wangdata/imageshare/blob/main//img/202204271948948.png?raw=true)

复制黏贴Github库的链接，creat project。这样就可以创建一个本地的git库。

#### 3.  安装和配置工具

##### 3.1 安装blogdown和静态网站生成器[hugo](https://themes.gohugo.io/)

```
install.packages('blogdown')

blogdown::install_hugo()
#可以升级
blogdown::update_hugo()
#安装主题
blogdown::install_theme("ahonn/hexo-theme-even") #任选，自定义，注意主题名需要在Github中寻找

#https://themes.gohugo.io/themes/hugo-theme-even/
```

![image-20220427201422246](https://github.com/wangdata/imageshare/blob/main//img/202204272014317.png?raw=true)



##### 3.2 链接RStudio, Git和Github

这一步非常关键，决定了我们是否可以将本地git文件同步到Github库。

在RStudio中, 找到 ***Tools > Global Options > Git/SVN***，确认git.exe位于RStudio指定的目录中

![image-20220427200522505](https://github.com/wangdata/imageshare/blob/main//img/202204272005560.png?raw=true)



创建SSH RSA密钥，在同一RStudio选项窗口中，单击**“Create RSA Key”，完成后单击“Close”。然后还是在这个窗口点击“View public key”**，复制全部数字和字符串。这样就是已经创建了一个属于自己的密钥

![image-20220427200621778](https://github.com/wangdata/imageshare/blob/main//img/202204272006835.png?raw=true)



将这个密钥提供给GitHub，这样以后在向RStudio中提交更改时，GitHub就会知道自己是谁。

所以需要**登陆GitHub,点击主页最右侧头像——settings——SSH and GPG keys**（如下面第一张图），不用管GPG key, 只用在SSH keys处点击New SSH keys（显示如下面第二张图），将刚刚在Rstudio创建并复制的密钥粘贴在第二张图片蓝色框框处并点击 Add SSH key。

![image-20220427200731459](https://github.com/wangdata/imageshare/blob/main//img/202204272007541.png?raw=true)

#### 4. 上传git目录文件

简单的可以通过RStudio中的git插件进行上传，可是我在使用的时候碰到主题无法上传的问题。原因是theme文件数超过100个。因此，只能通过bash窗口上传git目录文件。

以下是代码

```
git add files
git commit -m "asdf"
git push origin main
#可通过force强制上传，覆盖之前的文件
git push origin main --force
```

至此，我们已经将自己的文件上传至Github的库中。后期可以通过修改content中内容，对网页内容进行修改。

![image-20220427202057823](https://github.com/wangdata/imageshare/blob/main//img/202204272020869.png?raw=true)

#### 5. 部署自己的网页

这一步很简单，打开[Netlif.](https://app.netlify.com/sites/weiluwang/overview)。Add new site，按步骤操作即可。等待几分钟就可以创建自己域名的网站。

![image-20220427202321930](https://github.com/wangdata/imageshare/blob/main//img/202204272023982.png?raw=true)

![image-20220427202428633](https://github.com/wangdata/imageshare/blob/main//img/202204272024688.png?raw=true)

可以在**site setting**中修改域名信息。想拥有自己的独特的域名，可以购买付费服务。
