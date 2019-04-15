# 生命周期

## 说明

DuxPHP通过单入口进行执行，开发者需要对整个框架和项目的执行流程进行了解。

## 入口文件

用户发起访问请求首先执行"index.php"文件，入口文件中定义根目录常量与引入文件自动加载类，随后执行框架启动方法

```php
\dux\Start::run();
```

## 引导框架

启动框架时会执行框架基础运行环境的加载

1、定义常量

定义一些常用变量供框架与项目使用

2、设置环境

框架会根据不同的环境进行差异修正，在不同的运行环境达到统一的效果

3、加载配置文件

自动加载项目"data/config/global.php"目录下的配置文件

4、加载公共函数库

框架加载自带的常用函数库"'/kernel/Function.php'"供项目使用

5、执行框架引擎

配置加载基本信息后执行框架引擎进行启动

## 启动框架

引导框架结束后进行框架核心的启动操作

1、注册自动加载类

框架通过"spl_autoload_register"自动注册相关模块类减少手动进行"require"

2、接管异常处理

框架会自动接管PHP环境的异常进行统一处理报错、记录日志等操作

3、路由处理

进行Url解析根据解析到的参数设置不同的层、应用、模块和方法

4、运行模块

根据路由处理到的参数执行不同的模块方法

## 启动完成

框架启动完成后后续操作将交由项目模块进行处理，框架不定义过多规则与多余阻断，方便开发者进行不同需求的开发


