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
- MKNetworkKit  
MKNetworkKit 是一个使用十分方便，功能又十分强大、完整的iOS网络编程代码库，完全基于 ARC。它只有两个类, 它的目标是使用像AFNetworking这么简单，而功能像ASIHTTPRequest(已经停止维护)那么强大。  

#### 2017.1.4  
完成类似微信朋友圈点击图片放大，再次点击缩小，多张图片轮播效果。存在bug，轮播时候有的缩小没有动画效果。  
#### 2017.1.5  
GitLab是利用 Ruby on Rails 一个开源的版本管理系统，实现一个自托管的Git项目仓库，可通过Web界面进行访问公开的或者私人项目。它拥有与Github类似的功能，能够浏览源代码，管理缺陷和注释。可以管理团队对仓库的访问，它非常易于浏览提交过的版本并提供一个文件历史库。团队成员可以利用内置的简单聊天程序(Wall)进行交流。它还提供一个代码片段收集功能可以轻松实现代码复用，便于日后有需要的时候进行查找  
修改了轮播滚动评论图片缩小没有动画的bug，修改了长按粘贴汉化问题，评论日期显示仍然有问题，少了两个判断，一个是刚刚，一个是多少分钟前。  
#### 2017.1.6  
修改评论时间显示加两个判断一个刚刚一个多少分钟前。  
#### 2017.1.7/8  
这周末没怎么好好学习罪过  
#### 2017.1.9  
1.在initWithNibName中设置全局的HHUserDataCollectionService后再点击播放视频的方法中加入打点监听方法​。每次点击播放视频就能打点。  
2.修改UITextView的键盘returnKeyType为完成，点击完成后利用代理取消第一响应者隐藏键盘。  
3.调用UITextView的两个代理开始编辑和结束编辑，开始编辑cell的父控件向上移动self.textView.frame.origin.y个高度  
结束编辑向下移动​self.textView.frame.origin.y个高度。  
4.拼接self.commodityNum字段，购买种数一位数和两位数大小合适。待评价按钮显示待评价订单数量  
5.修改了评论图片在弱网络下可以继续选择的bug，SVProgressHUD工作时候禁止用户交互，但是可以点击返回按钮  
#### 2017.1.10  
1.弱网络情况下多次点击重复打点，利用cancelPreviousPerformRequestsWithTarget将打点代码放在外面两秒后相应  
2.修改了待评论的上次错误的修改，添加了waitcomment字段获取待评论数量  
3.利用HHSetButton在下面加了START文字，不同屏幕尺寸大小都合适  
4.收藏的绘本，点击编辑删除，返回到收藏界面，被删除的书已经存在，可以刷新  
5.添加了一个myBookrackCollectionWithOneBook:方法实现点击绘本查看，收藏的绘本，应该可以点击播放  今天就是修改了一些bug，不过修改的有些缓慢，但是还是从中了解了一些项目，和学到了知识。  
#### 2017.1.11  
1.修改了我的书架部分文案错误  
2.修改前天bug忘记dealloc注销通知  
3.添加商城首页的titleView右面反馈按钮，URL宏定义？  
4.点开一个订单详情界面界面缺少“我要反馈”显示在“联系客服”下面。对HHShoppingOrderDetailFooterView重新进行了布局，添加了feedBackView。  
#### 2017.1.12  
修改搜索分类  
#### 2017.1.13  
今日任务还没有确定。  
 工作10天总结下目前情况。每天上班会写一些分配的小任务，修改小bug，虽然做的有些慢，修改的也慢也修改的不是很好，但还是学到了一些知识。公司的人也很热心肠，很感谢。  
 但是有一个问题就是我从学校来之前想的是，白天上班在公司完成任务，晚上回去继续学习提高自己，但是现在晚上回去的有些晚，然后自己没有时间和精力再继续学习了，回去开始烧洗澡水，看一会手机，洗完澡几乎就可以睡觉了。这样我只能用周末的时间来提高了，我准备17号开始请假，然后回家大概20天时间，我准备好好利用这些时间，以前自己看小马哥视频写的百思不得姐还没有完成，看小马哥的视频确实给我很大的帮助，很感谢。  希望自己能够一直进步。  
 今天下午开始年会了，有点小兴奋那！  
#### 2017.1.14/15  
周末去学校那面取票，然后买了一些年货准备回家  
#### 2017.1.16  
今天新版本上架，还没有体验过怎样上架，学习！╮(╯_╰)╭  
今天没有预期的上架，伤心上午改了bug，下午写了打点  
#### 2017.2.10  
上班咯今天更加深入的了解了cocoapods  
instrument基本使用  
新注册了域名cocoacode.cn以后写文章就在这了  
#### 2017.2.13  
周一3.0开发开始了  
晚上看了下MJRefresh用法  
#### 2017.2.14  
今天开始写咔哒币账单记录页面  
#### 2017.2.15  
今天完成了账单界面  
#### 2017.2.16  
解锁界面还没有出来，自己学习  
#### 2017.2.17  
完成每日任务提醒界面  
完成部分绘本解锁界面  
#### 2017.2.19  
完成毕业设计文献综述  
#### 2017.2.20  
本周任务繁重啊  
遇见一个很好用的框架WZLBadge，能够设置自定义UITabBarItem和UIBarButtonItem的自定义小红点（可以自定义颜色、动画、数值等）  
#### 2017.2.21  
今天接口文档下来了开始拼接数据了  
#### 2017.2.22  
昨晚听大家讨论解决了网络请求的所有内存泄漏，今天还有NSString的copy和initWithFrame：CGRectZero等待修改  
#### 2017.2.23  
解决内存泄漏，矩阵APP上架。
#### 2017.2.24  
完成需求时间判定  
#### 2017.2.27  
周末完成了开题报告的所有文档  
这周准备用两到三天完成金币动画  
#### 2017.2.28  
完成金币降落加滑动效果，遇到瓶颈，UIView动画在运动中获取不到具体坐标点  
#### 2017.3.9  
来学校两天办了很多事哈哈，博客新地址也开通好了  
#### 2017.3.10  
博客、GitHubDemo分享处理初步完成，等待日常更新  
Swift、小乌龟的数据结构与算法持续学习  
#### 2017.3.14  
这周任务很多，矩阵app改版很大都是我自己改。完成了三分一了差不多。为27号做准备  
#### 2017.3.20  
学习iOS本地通知已经分享  
#### 2017.3.21  
这几天看下底层原理，框架实现等  
