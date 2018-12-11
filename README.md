# Android四大组件之Service

#### Service的概念
    Service（服务）是Android四大组件之一，主要用来响应和处理Activity的事件，Service是无界面的，不存在直接用户交互行为。(Activity需要layout布局文件)。
    
#### Service的特点
    1、Service是在后台执行，是用来响应Activity的事件请求的。
    2、Activity启动服务之后，即使Activity销毁（destory），服务也不会终止。（startService之后Service与Activity的生命周期并不会捆绑）
    3、Service在Android中是单例模式，OnCreate与OnDestory只会调用一次。
    4、当由于系统异常终止当前服务后，如果内存允许，服务所在的进程会重新创建。（用户主动销毁不会重新创建）
    
#### Service应用场景
    1、后台播放音频。
    2、下载网络数据（在Android3.x之后由于只支持子线程下载，因此此功能应该在子线程中启动服务）。
    3、访问文件、数据库等一些耗时业务逻辑功能，可以使用Service服务来实现。
    
#### Service启动三部曲
    1、创建一个类并继承系统Service。
    2、在AndroidManifest.xml文件中配置新创建的Service。（Service支持显示启动与隐式启动，可以通过配置action属性实现）
    3、通过Intent来启动服务。（startService(new Intent(...))）
