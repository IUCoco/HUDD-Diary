# HUDD-Diary  
## 红花朵朵工作每日总结  

### 2017.1.3  
#### 了解框架  
- CocoaLumberjack  
什么是CocoaLumberjack？  
CocoaLumberjack是一个很好用的日志打印工具，它可以帮助我们把工程中的日志信息打印到终端或者输出到文件中。  
什么是XcodeColors？  
XcodeColors是一个XCode插件，它配合CocoaLumberjack使用可以让将终端各种提示信息（error，warn……）按不同的颜色进行显示，一目了然。  
- MGJRouter  
MGJRouter方案  
蘑菇街通过MGJRouter实现中间层，通过MGJRouter进行组件间的消息转发，从名字上来说更像是路由器。实现方式大致是，在提供服务的组件中提前注册block，然后在调用方组件中通过URL调用block。  
MGJRouter组件化架构  
MGJRouter是一个单例对象，在其内部维护着一个“URL -> block”格式的注册表，通过这个注册表来保存服务方注册的block，以及使调用方可以通过URL映射出block，并通过MGJRouter对服务方发起调用。  
在服务方组件中都对外提供一个接口类，在接口类内部实现block的注册工作，以及block对外提供服务的代码实现。每一个block都对应着一个URL，调用方可以通过URL对block发起调用。  
在程序开始运行时，需要将所有服务方的接口类实例化，以完成这个注册工作，使MGJRouter中所有服务方的block可以正常提供服务。在这个服务注册完成后，就可以被调用方调起并提供服务。  
- pop  
[Pop动画教程](http://www.jianshu.com/p/47ce70f3bf59)  
- YYCache  
高性能 iOS 缓存框架。  
该项目是YYKit组件之一  
特性  
LRU: 缓存支持 `LRU (least-recently-used)` 淘汰算法。  
缓存控制: 支持多种缓存控制方法：总数量、总大小、存活时间、空闲空间。  
兼容性: API 基本和 NSCache 保持一致, 所有方法都是线程安全的。  
内存缓存  
对象释放控制: 对象的释放(release) 可以配置为同步或异步进行，可以配置在主线程或后台线程进行。  
自动清空: 当收到内存警告或 App 进入后台时，缓存可以配置为自动清空。  
磁盘缓存  
可定制性: 磁盘缓存支持自定义的归档解档方法，以支持那些没有实现 NSCoding 协议的对象。  
存储类型控制: 磁盘缓存支持对每个对象的存储类型 (SQLite/文件) 进行自动或手动控制，以获得更高的存取性能。  
- Library  
库(Library)直白一点说就是一段编译好的二进制代码,加上头文件就可以供别人使用;(例如: iOS中Objective-C编译下的.h和.m文件,打包静态库后会变为.h和.a文件)  
- UMSocial_6.1.1  
友盟分享  
- SCNavigation  
A custom navigation for pan gesture pop & maximum customization  
- AlipaySDK  
支付宝移动支付 SDK 标准版 from 2.0  
- XLPlainFlowLayout  
可以让UICollectionView的header也支持悬停效果，类似于tableView的Plain风格  
[Demo](http://www.code4app.com/ios/XLPlainFlowLayout/564422f7594b9023208b4a79)  
- JCAlertView  
简单的 AlertView 使用方法，版权模块  
- JNJProgressButton  
可直接在按钮内显示任务的执行进度  
- LDProgressView  
A flat or gradient progress view with a simple color setter and customizable options written in pure Core Graphics.  
LDProgressView 是一个扁平带梯度效果的进度条控件。可进行简单颜色设置和自定义选项，完全使用 Core Graphics 实现。  
- YYImage  
YYImage: 功能强大的 iOS 图像框架。  
支持以下类型动画图像的播放/编码/解码:  
WebP, APNG, GIF。  
支持以下类型静态图像的显示/编码/解码:  
WebP, PNG, GIF, JPEG, JP2, TIFF, BMP, ICO, ICNS。  
支持以下类型图片的渐进式/逐行扫描/隔行扫描解码:   
PNG, GIF, JPEG, BMP。  
支持多张图片构成的帧动画播放，支持单张图片的 sprite sheet 动画。  
高效的动态内存缓存管理，以保证高性能低内存的动画播放。  
完全兼容 UIImage 和 UIImageView，使用方便。  
保留可扩展的接口，以支持自定义动画。  
每个类和方法都有完善的文档注释。  
- EGOCache  
平常大多用SDWebimage做图片的缓存，如果做语音聊天SDWebimage就不太够用  
，所以推荐用EGOCache做文件缓存。  
EGOCache采用磁盘存储方式存储，如果文件使用频率很高可以缓存到内存中，减少io操作。  
1.EGOCache 作用  
EGOCache可以缓存实现了`<NSCodeing>`协议的对象、图片、语音、plist文件  
- YLGIFImage  
Asynchronized GIF image class and Image viewer supporting play/stop GIF images.  
异步加载GIF图片的类，支持GIF图片的播放与暂停。  
It just use very less memory. Following GIF usually will cost almost 600MB memory if it is fully decoded (800x600x389x4 Bytes), but using YLGIFImage, it just use about 30MB memory.  
它用的内存很少，完全解码GIF通常会消耗600MB的内存（800x600x389x4 Bytes），但是如果你用了YLGIFImage，它只占用30MB内存。  
- SSKeyChain  
SSKeyChains对苹果安全框架API进行了简单封装，支持对存储在钥匙串中密码、账户进行访问，包括读取、删除和设置。SSKeyChain的作者是大名鼎鼎的SSToolkit的作者samsoffes。  
项目地址：`https://github.com/samsoffes/sskeychain`
在工程中加入SSKeyChain  
在工程中加入Security.framework框架。  
把SSKeychain.h和SSKeychain.m加到项目文件夹。  
- WebViewJavascriptBridge  
实现OC与JS的交互  
- RSKImageCropper  
一个iOS图片裁剪器,支持横竖屏切换.  

 
