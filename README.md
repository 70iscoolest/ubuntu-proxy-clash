官网和网上其他教程不清不楚的，浪费我好几个小时！！！
特此记录一下

# 1. 下载客户端

 1. 创建`clash`文件夹以存放后面所需的所有文件
 
 	终端执行(用户目录下)
	```
	cd && mkdir clash
	```
	在*用户目录*下创建**clash**文件夹
 2. [下载Clash二进制文件](https://github.com/Dreamacro/clash/releases)
![在这里插入图片描述](https://img-blog.csdnimg.cn/d04292718a244ffe8619883fe5f637a3.png)
个人64位电脑下载**clash-linux-amd64-v1.16.0.gz**即可
3. 将其解压缩并重命名为clash
	

# 2.  下载clash配置文件
在终端 cd 到 clash 二进制文件所在的目录，执行`wget -O config.yml http://***`

> 说明：http://**是代理网站的SSR链接

> **踩的第一个坑：执行语句后，新生成的`config.yml`文件并没有下载下来任何东西。**
> 解决办法：切换成root用户，重新执行该语句。

在文件夹下出现了两个新文件：`config.yml`和`wget-log`
# 3. 启动clash

```
./clash -d .
```
> **踩的第二个坑：提示*permission denied***
> 解决办法：运行权限`chmod +x clash`

> **踩的第三个坑：提示`Can‘t find MMDB, start download错误`**
> 说明：按理说，它应该自己下载MMDB文件，但不知道为什么下载不了，所以需要我手动下载
> 解决办法：1. [下载MMDB文件](https://gitee.com/dnqbob/sp_engine/blob/SPcn-01-02-20/GeoLite2-Country.mmdb.gz)，解压缩并重命名为`Country.mmdb`
> 2. 再次执行`./clash -d .`

> **踩的第四个坑：新生成了`config.yaml`文件, 打开只有一条内容：`mixed port: xxxx`**

> **说明：真的无语，官网不会写教程就不要写，竟然漏了最重要的一步：
> 把配置文件`config.yml`的内容替换到`config.yaml`文件里面！！！**

最后两步：
1. 在ubuntu系统设置网络连接中配置代理：
![在这里插入图片描述](https://img-blog.csdnimg.cn/f44cfc2c8ffa49209ae4f260ed0b4781.png)
networkproxy改为手动，参照`config.yml`文件内容如图配置：
![在这里插入图片描述](https://img-blog.csdnimg.cn/0c216ca9fe3b4f13a593593d4066bc4c.png)
> 说明：每个人的代理服务不同，具体设置请查看所购买服务的网站说明

2. 然后再次启动clash: 

终端输入：
```
./clash -d .
```

终端窗口出现：

![在这里插入图片描述](https://img-blog.csdnimg.cn/b4fa45ba28db450c9edaa5d7ba23316c.png)

> **至此成功！**
