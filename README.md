# buglyHotfixDemo
bugly热修复demo
### 说一下坑
#### 1. 记得将as中的instant run 关闭    as3.5之后 关闭hotswap
#### 2.Caused by: com.tencent.tinker.build.util.TinkerPatchException: there's loader classes added in new primary dex

这个问题 在tinker-support.gradle文件中添加ignoreWarning = true即可
#### 3.基版本的版本等信息不上传的问题   安装基版本后  后台检测不到基版本对应的版本号
解决： 有些机型 需要添加上这行代码才行
Beta.init(getApplication(),true);
#### 还有就是网络问题 Google针对 Android 系统(Android P) 的应用程序，将要求默认使用加密连接（TLS），目的是为了保证用户数据和设备的安全，
因此在Android P系统中使用HttpUrlConnection进行http请求会出现上述问题。这个解决方法就是在清单文件中的application中的networkSecurityConfig字段
自定义配置即可

### 补丁包下发后 需要等待10分钟左右才生效
## 最后 还有一个需要注意 就是每次发上线的基准包后  基准包相关的信息一定要备份
