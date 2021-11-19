## SmartHttp

一款基于RxJava2+Retrofit3+OkHttp3实现的网络请求框架，采用Builder链式调用，集成cookie管理，多种缓存模式，极简https配置，
上传下载进度，请求错误自动重试，请求携带token、时间戳、签名动态配置，自动登录成功后请求重发功能，3种层次的参数设置默认全局局部，
默认标准ApiResult同时可以支持自定义的数据结构，已经覆盖几乎所有的网络请求。

*注：Retrofit2和Rxjava3都是非常火爆的开源框架，本库就不过多介绍Retrofit2和Rxjava3的用法了。*

## 创建缘由
网上好的开源网络库像Volley、async-http、OkHttp、Retrofit等都非常强大，但是实际应用中我们不会直接去使用，一般都会根据自己的
业务再封装一层，这样更方便快捷，又能统一处理业务共性的东西例如：统一的数据结构（code、msg、data）、token处理、网络异常等情况。
在使用Retrofit来请求网络的时候，项目的需求越来越多，Api也随之越来越多，一个普通的应用Api一般也在100+左右。如果把这些api放在一
个ApiService内会很臃肿，不利于查看Api.如果采用模块的方式对Api进行分类，每个模块对应若干个Api。以retrofit的使用方式又需要创建
若干个ApiService，这种方式维护方便，但是模块增多了，类也增多了很多。对于懒人来说就想通过一个URL就能回调你所需要的数据，什么
ApiService都不想理会，同时又可以很快的与自己的业务相关联，就类似于代替你在开源网络库基础上再封装一层的作用，于是本库就应运而生。

## 项目特点
- 比Retrofit使用更简单、更易用
- 采用链式调用一路到底
- 加入基础ApiService，减少Api冗余
- 支持动态配置和自定义底层框架OkHttpClient、Retrofit
- 支持多种方式访问网络GET、POST、PUT、DELETE等请求协议
- 支持网络缓存,八种缓存策略可选，涵盖大多数业务场景
- 支持固定添加Header和动态添加Header
- 支持添加全局参数和动态添加局部参数
- 支持文件下载、多文件上传和表单提交数据
- 支持文件请求、上传、下载的进度回调、错误回调，也可以自定义回调
- 支持默认、全局、局部三个层次的配置功能
- 支持任意数据结构的自动解析
- 支持添加动态参数例如timeStamp时间戳、token、签名sign
- 支持自定义的扩展Api
- 支持多个请求合并
- 支持Cookie管理
- 支持异步、同步请求
- 支持Https、自签名网站Https的访问、双向验证
- 支持失败重试机制，可以指定重试次数、重试间隔时间
- 支持根据Key删除网络缓存和清空网络缓存
- 提供默认的标准ApiResult解析和回调，并且可自定义ApiResult
- 支持取消数据请求，取消订阅，带有对话框的请求不需要手动取消请求，对话框消失会自动取消请求
- 支持请求数据结果采用回调和订阅两种方式
- Api设计上结合Http协议和Android平台特点来实现，Loading对话框，实时进度条显示
- 返回结果和异常统一处理
- 结合RxJava3，线程智能控制


