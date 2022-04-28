typora作为一款美观轻量的markdown编辑软件，用于做笔记特别方便，美中不足的地方就在于不能云保存图片。每次我想将笔记上传至博客的时候，看到很多图片无法上传，都会有深深的无力感。

后来发现typora提供了picgo+github自动上传图片的方法以解决上述问题，完成相关的配置以后，typora就能正常云上传图片，并且也能正常地把图片上传到博客中。

不过配置环境的步骤略微繁琐，所以我在配置成功后写下详细的配置步骤，希望对大家有帮助。

安装要求
Typora + Picgo + github账号

Typora尽量安装最新版本，以往的老版本可能不支持picgo上传图层，安装链接：https://www.typora.io/

Picgo也尽量安装新版本，安装链接：https://github.com/Molunerfinn/PicGo/releases

配置步骤
创建github账号 -> 如下方式添加仓库 -> 配置仓库


获得Personal access token(私人令牌)


注意：获得的私人令牌要自己保存好，github不会再明文显示你创建好的令牌！



下载Picgo -> 图床设置 -> Github图床 ->配置信息 -> 设为默认图层 -> 确定



GIthub设置格式：

设定仓库名（格式）：用户名 + 仓库名
设定分支名：一般填上master
设定Token：填入私人令牌
指定存储路径：一般填上img
设定自定义域名（格式）：https://github.com/wangdata/imageshare/blob/main/
PS：建议在PicGO设置中只选择显示Github图床。

关闭github网页 -> 进入typrao偏好设置 -> 选择图像 -> 按下图进行设置 (PicGo路径指向exe文件)-> 验证图片上传选项

这样就配置成功了！

回到Picgo相册会找到刚刚验证上传的typora图标，说明配置成功！(其他的是我写这篇笔记的图片)

还存在一个问题，上传后的图片无法正常在本地显示。查了资料，最终通过在完整路径之后添加**?raw=true**得以解决。


