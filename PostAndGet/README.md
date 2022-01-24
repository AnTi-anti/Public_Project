###  PostAndGet
Post和Get发包小工具

#### 编程语言
* c#

#### 如何使用

##### 直接使用
* 下载编译好的ex文件：[文件地址](https://github.com/AnTi-anti/PostAndGet/tree/main/PostAndGet/PostAndGet/bin/Release)

##### 自己修改代码
* 下载VS,导入文件即可


#### 本工具简要说明：
* 1.本在线工具支持接口http post,get,put,,head,options等请求，支持带cookie header和ip代理请求
* 2.可以生成api接口的文档，本站同时提供api接口压力测试和websocket测试。 2.访问要登录的接口的时候，可以手动填写cookie。或者在谷歌浏览器中访问这个接口域名，按F12,在network下， 图示,直接复制填写到本工具的cookie中。就可以带cookie访问，不用手动填写
* 3.header 可以手动输入(自定义的header信息)。也可以在浏览器的network中拿到header信息，直接填到本工具的header输入框中。

#### 白话一下http请求：
http接口测试和使用，首先要了解什么是http请求：
http请求通俗讲就是把客户端的东西通过http协议发送到服务端，服务端根据http协议的定义解析客户端发过来的东西！

http请求中常用到的是get和post请求参数，get参数是拼接在url得后边，以"?"连接域名和参数，形成get请求，例如：http://coolaf.com?a=b&c=d, 问号后边的就是get请求参数，post请求不会在url中看到，会放到http请求的body中，各大语言都会封装出函数，在body中解析出post请求参数。那post参数是什么样子呢？它可以是任何形式，常见的key=value的形式，和get请求格式一样"a=b&c=d" 这种，另外json,xml格式也是常见的。

这些格式在传递的时候，会受到Content-Type影响，不同的Content-Type传递格式不一样，服务端就会根据Content-Type进行相应格式的解析。客户端和服务端就是通过这些协议来分辨传递的是什么格式的。一定要了解下常见的Content-Type，更多的请见上边Content-Type链接说明。

Content-Type：application/x-www-form-urlencoded，类似form表单和get,post请求都是这个，格式如 "a=b&c=d",服务端会自动解析

Content-Type：application/json 如果要发送json格式，request header中就需要加入这个Content-Type类型，这种形式的服务端的接受不太一样，一般不会解析到post请求中，一般需要读取body流的方式获取。

上边是常见的两种传输格式，我们自己写代码的时候有时候不用写，那是因为类库中，有的已经自动给加入啦，所以不需要自己加，Content-Type很重要，他影响你传递的格式。

http 请求中还要注意的就是header,分为request header 和response header,request header是客户端请求的时候发送的，告诉服务器你客户端的情况，需要服务端怎么返回给你，例如，是否压缩（Accept-Encoding:gzip, deflate, sdch）这个就是告诉服务端，我支持这些种压缩，你返回的时候，你可以选择一种对数据压缩，我可以解开。还有是否缓存，接受的语言，User-Agent，referer等，cookie也是放到request header中传递到服务端的，从而实现登录。所以request header 是告诉服务端你有什么或者参数传递的，上边这些都是http协议定义好的，大家都按这个规则解析就好，另外header都是可以自定义的，你可以加入任何变量到里边。所以header中信息是可以任意修改，发送到服务端的。

response header 相对request header，就是服务端给客户端的信息，有些是服务端根据客户端的需求给的响应，有的服务端告诉客户端的一些其他信息，例如，请求协议，请求状态码，是否缓存，
设置cookie也是有response header中返回，浏览器接收到就会设置到浏览器中。

白话这么多，有什么错误或者问题，可以给我留言。

#### 参考文献
* http://www.ouapi.com/

#### 作者博客(欢迎follow)
* https://blog.csdn.net/weixin_35770067
