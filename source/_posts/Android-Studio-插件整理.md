---
title: Android Studio 插件整理
date: 2017-04-20 22:48:28
tags:
---

### Android Layout ID Converter

    用途：findViewById
    使用方式：右键layout 里面的xml 文件，Convert Android layout xml

### SelectorChapek

    用途：状态选择器的生成
    使用方式：把图片拷贝到drawable里面，右键文件夹，Generate Android Selectors

### Android Code Generator

    根据布局文件快速生成对应的Activity，Fragment，Adapter，Menu。

### Android Methods Count 

    显示依赖库中得方法数

#### CodeGlance

    在右边可以预览代码，实现快速定位

#### GenerateSerialVersionUID
    
    实现Serializable序列化bean

#### dagger-intellij-plugin 

    dagger可视化辅助工具

#### AndroidProguardPlugin

    一键生成项目混淆代码插件，值得你安装~(不过目前可能有些第三方项目的混淆还未添加完全)

#### otto-intellij-plugin 
    
    otto事件导航工具

#### Android-DPI-Calculator 
    
    DPI计算插件

#### .ignore

    我们都知道在Git 中想要过滤掉一些不想提交的文件，可以把相应的文件添加到.gitignore 中，而.gitignore 这个Android Studio 插件根据不同的语言来选择模板，就不用自己在费事添加一些文件了，而且还有自动补全功能，过滤文件再也不要复制文件名了。我们做项目的时候，并不是所有文 件都是要提交的，比如构建的build 文件夹，本地配置文件，每个Module 生成的iml 文件，但是我们每次add，commit 都会不小心把它们添加上去，而gitignore 就是解决这种痛点的，如果你不想提交的文件，就可以在创建项目的时候将这个文件中添加即可，将一些通用的东西屏蔽掉

#### CheckStyle-IDEA 

    CheckStyle-IDEA 是一个检查代码风格的插件，比如像命名约定，Javadoc，类设计等方面进行代码规范和风格的检查，你们可以遵从像Google Oracle 的Java 代码指南 ，当然也可以按照自己的规则来设置配置文件，从而有效约束你自己更好地遵循代码编写规范

#### WakaTime

    记录你在IDE上的工作时间

#### adb-idea

    支持直接在AS面板中进行ADB操作

#### lint-cleaner-plugin

    https://github.com/marcoRS/lint-cleaner-plugin
    移除Android中无用资源

#### dexcount-gradle-plugin

    方法数计算，对于较大应用避免方法爆棚很有用

#### JsonOnlineViewer

    可实现直接在android studio中调试接口数据，可以选择请求类型，自定义请求头及请求体，json数据格式化后展示
    
#### Android Drawable Importer

    为了适应所有Android屏幕的大小和密度，每个Android项目都会包含drawable文件夹。任何具备Android开发经验的开发人员都知道，为了支持所有的屏幕尺寸，你必须给每个屏幕类型导入不同的画板。Android Drawable Importer插件能让这项工作变得更容易。它可以减少导入缩放图像到Android项目所需的工作量。Android Drawable Importer添加了一个在不同分辨率导入画板或缩放指定图像到定义分辨率的选项。这个插件加速了开发人员的画板工作。

#### AndroidCodeGenerator

    可以生成ViewHolder和findView方法的代码。尤其是在Adapter实现类的getView当中很有用。
    
#### Codota

    搜索最好的Android代码。他的搜索源，不仅只有Github，而且还有知名博客和开发者网站，让你搜索一个东西，不用在找上半天；除了搜索功能，首页的下方还罗列比较流行的类库，还提供保存代码的CodeBox，同时还提供了Chrome 插件和Android Studio 插件，最后通过Google，Github，Facebook 任意一个授权登录即可使用；而且当你点击搜索的结果（Java class）的时候，右侧会显示UML 视图，而且左边的代码如果点击会有高亮现实，而且还会显示Doc，并提供了API Doc 的链接
    
#### Settings Repository：

    不同设备之间同步Android Studio的配置。

#### GsonFormat

    根据Gson　api接口生成相应的实体类

#### jimu Mirror

    Android Studio配备了一个可视化的布局编辑器。但是一个静态的布局预览有时候对于开发人员而言可能还不够，因为静态预览不能预览动画、颜色和触摸区域，所以jimu Mirror来了，这是一个可以让你在真实的设备上迅速测试布局的插件。jimu Mirror允许在设备上预览随同编码更新的Android布局


#### ADB WIFI
    
    Android wifi无线调试App
    
#### .LayoutFormatter

    drakeet 开发一个一键格式化你的 XML 文件的 Android Studio 插件，至于为什么不用 Android Studio 自带的格式化功能而用这个插件，
可以看下作者的一篇 Blog -> [当我们谈 XML 布局文件代码的优雅性](https://drakeet.me/layoutformatter)

#### MVPHelper

    一款Intellj IDEA 和Android Studio的插件，可以为MVP生成接口以及实现类，解放双手。
具体请查看[Android Studio插件之MVPHelper](http://androidwing.net/index.php/27)，一键生成MVP代码一文

#### MultiTypeTemplates

    生成MultiType和itemviewprovider
-> [关于MultiType请查看Android 复杂的列表视图新写法 MultiType](http://gank.io/post/5823bcf6421aa90e799ec2ad)

#### JVM Debugger Memory View

    Android Studio和IDEA中一个很有用的内存调试插件
详细可参考说一说[Android Studio和IDEA中一个很有用的内存调试插件](https://zhuanlan.zhihu.com/p/25110433)

#### ReciteWords

    这是一个androidStudio翻译与陌生单词记录插件
    你所翻译的单词会被记录在你当前用户目录下的ReciteWords.md文件中（如:C:\Users\Bolex\ReciteWords.md）。可以通过Markdown编辑器打开它进行学习。



## 查看应用的方法数
查看library的方法数的方法是使用 Dexcount gradle plugin ，只需要在app/build.gradle中集成：

```
buildscript {  
    repositories {  
        jcenter() // or mavenCentral()  
    }  
  
    dependencies {  
        classpath 'com.getkeepsafe.dexcount:dexcount-gradle-plugin:0.6.2'  
    }  
}  
// make sure this line comes *after* you apply the Android plugin  
apply plugin: 'com.getkeepsafe.dexcount'

```
