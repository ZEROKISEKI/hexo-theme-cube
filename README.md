# hexo-theme-cube


## 介绍


之前用Laravel写了一个博客, 然而用起来不是那么顺手, 而且很久没写Laravel了, 不想再维护, 于是决定用回Hexo, 找了几个主题, 但是都不是特别喜欢, 主要感觉太过简约了(手动滑稽), 于是就打算自己来写一个主题, 也算是练练手了. 这个主题是最终gulp打包的结果, 如果要看源代码, 可以看我的另一个项目[cube-generator](https://github.com/ZEROKISEKI/cube-generator), 如果要做什么改动, 也是在那个项目上进行改动生成.


    git clone https://github.com/ZEROKISEKI/hexo-theme-cube.git themes/cube --depth 1


## 演示


主题示例地址: [http://sora1.coding.me/](http://sora1.coding.me/)


### 搜索功能


![搜索功能](http://ouo1ro65u.bkt.clouddn.com/%E6%90%9C%E7%B4%A2%E5%8A%9F%E8%83%BD.png)


搜索框的设计样式参考了[ppoffice](https://github.com/ppoffice/hexo-theme-icarus)的设计样式,只要进行输入即可进行对应的搜索, 此功能需要在您的Hexo站点上进行`hexo-generator-json-content`的安装和设置

    npm install hexo-generator-json-content --save
    
然后在您的Hexo站点的`_config.yml`(非主题的`_config.yml`)上进行对应的设置:

    jsonContent:
      pages:
        title: true
        text: true
        path: true
        preview: true
      posts:
        title: true
        text: true
        path: true
        preview: true

您可以在`hexo new`或者`hexo new page`生成md文件后往`front-matter`(不知道是什么可以上[Hexo官网](https://hexo.io/)看下)添加对应的`preview`地址:

    preview: http://ouo1ro65u.bkt.clouddn.com/图片预览.png

效果图如下:


![图片预览](http://ouo1ro65u.bkt.clouddn.com/%E5%9B%BE%E7%89%87%E9%A2%84%E8%A7%88.png)



### 代码高亮


代码的高亮采用了[highlight.js](https://github.com/isagalaev/highlight.js), 如下图为代码风格设置
为`vs2015`的风格:



![代码高亮](http://ouo1ro65u.bkt.clouddn.com/%E4%BB%A3%E7%A0%81%E9%AB%98%E4%BA%AE.png)



您可以进行代码风格的配置，不过要在[cube-generator](https://github.com/ZEROKISEKI/cube-generator)重新进行主题的生成(该项目有对应的文档说明)


### 音乐模块


音乐模块采用了[DIYgod](https://github.com/MoePlayer/APlayer)的开源项目[APlayer](https://github.com/MoePlayer/APlayer), 您可以将您喜欢的音乐列表配置在您的博客上，演示效果如下:



![音乐模块](http://ouo1ro65u.bkt.clouddn.com/%E9%9F%B3%E4%B9%90%E6%A8%A1%E5%9D%97.png)



侧边栏可以选择开启歌词或者关闭歌词, 相关的音乐配置在主题的`_config.yml`上面, 具体说明可以参考下面的**配置说明**


### lightgallery


该主题采用了[lightgallery](https://github.com/sachinchoolur/lightGallery)进行图片展示，效果如下(展示在做这个主题之前, 我都不知道有lightgallery这个东西2333):


![lightgallery](http://ouo1ro65u.bkt.clouddn.com/lightgallery.png)


目前使用了lightgallery出现的一个问题是在我的小米4原生浏览器图片貌似是加载不出来的, 这个问题待有时间再调试


## 配置说明

以下所指的`_config.yml`均为主题的`_config.yml`!

### 背景模块

背景模块在`_config.yml`的主要参数如下:
    
    header:
       background: http://cube-1252774894.cosgz.myqcloud.com/background.png
       title: senrenbankaの部落格
    background: http://cube-1252774894.cosgz.myqcloud.com/background.png
    position: 400
    blur: 5        
   
`header.background`和`background`分别指移动端和PC端的背景图, 你可以让两个值都为同一个url, 或者分开两个url(当然路径也可以, 见`_config.yml`的说明)
    
`header.title`为博客标题(中间动态加载的文字, 参照了DIYgod博客的效果, 自己做的比较搓)
    
`position`为图片的定位, 如果`position`为0, 则表示图片全部显示
    
`blur`为顶部导航栏的模糊度, 您可以修改该值来达到一个比较满意的模糊度
    

### 开启搜索功能

开启搜索功能除了在上面提到的要在Hexo站点配置`hexo-generator-json-content`之外,还要在`_config.yml`进行配置:
    
    search: true
           

### 音乐模块

在本项目的`_config.yml`我们可以看到
    
    music:
      - title: Dear friends
         author: TRIPLANE
         source: http://cube-1252774894.cosgz.myqcloud.com/music/source/TRIPLANE - Dear friends.mp3
         lrc: http://cube-1252774894.cosgz.myqcloud.com/music/lrc/Dear friends - TRIPLANE.lrc
         image: http://cube-1252774894.cosgz.myqcloud.com/music/image/TRIPLANE - Dear friends.jpg
      - title: Butter-Fly
         author: 和田光司
         source: http://cube-1252774894.cosgz.myqcloud.com/music/source/和田光司 - Butter-Fly (ピアノヴァージョン).mp3
         lrc: http://cube-1252774894.cosgz.myqcloud.com/music/lrc/Butter-Fly (ピアノヴァージョン) - 和田光司.lrc
         image: http://cube-1252774894.cosgz.myqcloud.com/music/image/和田光司 - Butter-Fly (ピアノヴァージョン).jpg
      - title: 宵闇花火
         author: 葉月ゆら
         source: http://cube-1252774894.cosgz.myqcloud.com/music/source/葉月ゆら - 宵闇花火.mp3
         lrc: http://cube-1252774894.cosgz.myqcloud.com/music/lrc/宵闇花火 - 葉月ゆら.lrc
         image: http://cube-1252774894.cosgz.myqcloud.com/music/image/葉月ゆら - 宵闇花火.jpg
    
     
source, lrc, image 可以填路径或者url, 下面是填路径时对应的地址:
    
    
    source -> source/music, 示例: source: music1.mp3 意味着你的音乐的路径是 source/music/music1.mp3
    lrc -> source/lrc, 示例: lrc: music1.lrc 意味着你的音乐的路径是 source/lrc/music1.lrc
    image -> source/images/music 示例: image: music1.jpg 意味着你的音乐的路径是 source/images/music/music1.jpg
    
如果使用路径的话在本地测试会出现音乐无法播放或者`Error happen`的情况(用url可能也会, 在`APlayer`的代码中表示下载失败的错误, 这锅表示不背), 所以最好的情况是用cdn url引用而不是路径
    
如果音乐配置没有设置对应的`image`, 那么默认使用`source/images/music/default.jpg`(图片可以换成你想要的)
    
注意! 如果引用cdn url, 那么要开启跨域访问(access-origin为您的域名, 因为`APlayer`对lrc的加载采用的是XMLHttpRequest)
    
关于音乐的设置:
    
    music_setting:
      auto: false                       //true为自动播放, 默认为false
      mode: circulation                 //circulation为循环播放, 可填的值为random,single,order等
      narrow: false
      mutex: true
      showlrc: true                     
      theme:                            //设置音乐模块颜色, 默认为#b7daff
      preload: auto                 
      maxHeight: 513px                  //这个可以不用改动
          
这个配置其实是配置`APlayer`的, 具体的说明和参数选择可以直接看[文档](https://aplayer.js.org/docs/#/)
    
    
### 头像风格
    
    avatar: true        //为true时表示头像为圆框, 否则为方框
        
    
### 友链默认头像

    friend_links: friend_links.jpg  // 指向source/images/friend_links.jpg, 你可以自己定制修改路径
       
        
## 写在最后


这个项目是目前实习阶段抽空做的, 近段时间估计不怎么更新修改维护(白天实习, 晚上毕设有点忙), 9月份之后估计就有空了,这个主题项目是由[cube-generator](https://github.com/ZEROKISEKI/cube-generator)生成的, [cube-generator](https://github.com/ZEROKISEKI/cube-generator)的gulp构建比较蛋疼, 里面的JS代码也很乱, 预计后面再改, 如果你想看原来的主题代码, 那么可以关注下[cube-generator](https://github.com/ZEROKISEKI/cube-generator)

