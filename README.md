## Spring cloud 配置中心服务端（Demo）

本程序为Spring cloud配置中心服务端demo工程。该demo基于spring官方demo编写。

### Spring cloud 配置中心说明

* 配置版本管理：基于git、svn形式实现版本管理。可以使用github、gitlab、svn等等。

* 配置管理：存储在github上的文件以properties文件格式存放。不用打散存储，符合程序员习惯。

* 多应用多环境配置支持：使用{AppName}-{Profile}.properties 方式实现多应用多环境配置。

* 提供restful api接口。可以使用http://{host}:{port}/{appName}/{profile}方式访问具体应用。例如：http://localhost:8881/foo/development。

* 配置继承： 可以使用复合环境库实现公共配置可被集成（其实就是多个配置组合成一份配置文件）。

* 配置加密：可实现配置内容加密传输。不过比较麻烦。

* 权限控制：只能靠版本控制软件自身提供的权限系统实现权限控制。

* 配置实时更新：可以结合Spring bus 实现客户端配置实时更新。

* 集群：可以自己实现集群部署。

主要缺点：
* 对于需要按照应用控制访问权限，比较麻烦。
* 和spring程序集成度比较高。其他异构语言可以通过restful api，但是比较麻烦。

### 运行本用例

在IDE中，可以直接编译运行ConfigServerApplication.java 文件。
运行后，可以获取配置中心配置，如或者应用“foo”下的“development”环境配置。可以访问 http://localhost:8881/foo/development 获取配置。

服务器配置文件，参考： https://github.com/spring-cloud-samples/config-repo

