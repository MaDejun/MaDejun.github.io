> 虽然搭建博客主要是为了记录自己兴趣爱好的学习经验和偶尔的日常小生活，但有个相册的功能也没有多大的违背搭建博客的初愿。

效果: [看这里](http://www.madejun.top/photos)
说明:如果你会前端，可以自行改一下样式。
<!--more-->
# 功能实现
1.首先你要找一个可以存储图片的地方，如果你用github，最好新建一个仓库用于存储图片，可以访问到的。不要在博客的仓库上存储，这样会拖累它的速度的。例如我新建的仓库名叫Blog-Back-Up,当然你也可以用七牛
![](http://upload-images.jianshu.io/upload_images/3709167-ca59dcea4fe5b7b2.jpg)

2.要生成photos.html来展示自己的图片。也要向这个页面提供图片的数据，这些数据的来源就需要一些文件来生成一个.json (里面有图片的信息)文件。

>2.1本地目录里的设置 

2.1.1 进入到你的博客目录下生成photos页面 执行"hexo new page "photos" "
![图片发自简书App](http://upload-images.jianshu.io/upload_images/3709167-db7ea608d983e27e.jpg)


2.1.2 可以在[lawlite 19](https://github.com/lawlite19/Blog-Back-Up/tree/master/blog_photos_copy)这里下载样式文件，将这些文件放到你刚刚新建的/source/photos文件夹里。
![](http://upload-images.jianshu.io/upload_images/3709167-457ebfda1c25aa61.jpg)



然后在博客的根目录下新建photos和min_photos两个文件夹，photos用来存放你要上传的照片，min_photos文件夹不需要你去处理什么 里面会在你执行脚本的时候自动将处理后的图片放进去。



修改ins.js文件里面的rend函数下的url
![](http://upload-images.jianshu.io/upload_images/3709167-4bab308a9ede818a.jpg)
**前面一定是raw.githubusercontent.com**

2.1.3 这一步就该处理图片了，处理图片所用到的**python脚本文件**你可以到[这里](https://github.com/lawlite19/Blog-Back-Up)下载


下载后放到你的博客根目录下，将你要上传的图片放到photos文件夹里，并且将图片重命名为一下格式
**最前面是日期，然后用下划线进行分隔
后面是图片的描述信息，注意不要包含_和.符号**
![](http://upload-images.jianshu.io/upload_images/3709167-7b2fc4778b9aed09.jpg)

通过命令窗口进入到tool.py所在的目录执行tool.py脚本，执行结束后，你就会在/source/photos文件里看到一个data.json文件。


最后

hexo g
hexo s
预览一下 成功后就可以hexo d部署到博客上了



