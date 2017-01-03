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
