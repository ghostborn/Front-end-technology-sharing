> **cros(跨域资源共享)**

它通常是在`同源策略`的上下文中，这是由web浏览器实现的一项安全功能。
它会阻止网页发出跨域请求，目的是防止恶意网站对其他域上的敏感资源发出未经授权的请求。

对于`HTTP`, **源**由`URL`的以下部分组成:

- 协议 （eg: http或https）
- 主机名 （eg: apple.com）
- 端口 （eg: 80、3000）

只有这三项都匹配，浏览器才会认为这两个`URL`是同源的，否则就视为跨域。



> **如何解决跨域问题**

- **服务端请求头`Access-Control-Allow-Origin`设置 '*'（允许所有地址跨域访问），或者单独设置`origin`(请求地址)**

  

- **nginx通过反向代理解决跨域原理是利用服务器请求服务器不受浏览器同源策略的限制**

​      客户端请求nginx服务器，在nginx.conf配置文件中配置server监听客户端的请求，然后把location匹配的路径代理到真实的服务器，

​      服务器处理请求后返回数据，nginx再把数据给客户端返回

![](https://github.com/ghostborn/Picture/blob/main/202409211449657.png?raw=true)



- **window.postMessage()**
- **WebSocket**
- **jsonp的原理就是利用了script标签不受浏览器同源策略的限制，然后和后端一起配合来解决跨域问题的。**

