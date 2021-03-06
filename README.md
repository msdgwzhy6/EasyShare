# EasyShare
一个Android社会化分享脚手架，集成微信，qq，微博分享。

# 作用 
这是个Android社会化分享脚手架，利用抽象工厂，模板方法封装的一个简单易定制的分享组件，不能代替ShareSDK等商业化SDK使用，仅供开发交流探讨，不建议线上项目直接使用。  

# 架构 
![](https://imagesforblog.oss-cn-beijing.aliyuncs.com/Sharelib.png)  
 * callback-回调接口定义 
 * factory-工厂类，顶级抽象工厂定义生产的所有平台的分享数据函数，子类工厂生产对应的数据类型，新增分享数据类型时需要新增子类工厂生产对应的IShareMode。  
 * model-模型类，顶级接口为IShareModel，分享数据所需要的数据模型，在此处新增需要分享的数据模型。    
 * platform-分享目标平台，ISharePlatform是目标平台接口，所有衍生平台需实现该接口， 当接入新的分享平台时，需要在此处进行扩展。  
 * type-分享数据类型的封装，分享的入口，顶级接口IShareContentType，持有Share行为,当需要分享的类型发生变化时，需在此处实现新的IShareContentType类型。   
 * wxapi-包名必须是项目包名，此处只做演示参考用。  
 * IShareDialog.java-分享选择弹窗的接口类，需在项目中使用的弹窗中实现该接口。  

# 集成步骤
 1. clone该仓库  
 2. 参考DemoActivity  
  
# 新增分享类型
 1. 新增IShareModel接口实现类  
 2. 新增IShareContentType接口实现类
 3. 新增抽象工厂子类生产对应数据进行分享
  
# 新增分享平台 
 1. 引入对应平台依赖libs   
 2. 新增ISharePlatform接口实现类   
 3. 修改factory抽象类及其子类   
 4. 修改IShareDialog子类实现，新增点击事件   
