wx小程序总结

小程序是微信开发的技术,一经问世就爆火

类比html5记忆

目录结构wxml,js,wxss,json

wxml  模板文件 (html)

js   脚本逻辑文件       (js)

json 页面配置文件 

wxss  样式文件(css)

app.js 小程序入口文件 全局唯一变量app,

pages文件夹放置文件 

生命周期:  小程序的状态不同,相对应的生命周期函数也不同,

比如onload 加载 onshow显示  onhide  隐藏 

 变量,值传递

语法:{{ }}  wx:if,wx:for wx:else,wx:elif ,wx:key,  if else elif 都一样,著不过加上了wx:

页面配置:

​	全局配置:window配置 

​	具体的配置会覆盖全局的配置

tabbar配置,加的功能之类的卸载tabbar中

小程序的有状态和无状态服务,,,

http协议是无状态的,但小程序是Storage存储cookiesdjango存储session,通过wx服务器转发到第三方后台,wx服务器不存储信息,

用户体系构建 :

openid

前台获取code,wx.request()发送code,先访问微信服务器,微信服务器返回code,小程序和django后台通信 django发送code+appid+secretkey到微信服务器.wx发送cookiesessionopenid到djago,django后台获取用户的状态(给用户添加额外的描述信息)

用第三方组件 weUI 

@import 路径 cv

绑定时间 bindxxxxx='函数名'   没写一个<view> 都可以绑定一个函数

wx.request(){}网络请求