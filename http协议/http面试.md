# HTTP/0.9
    - 超文本传输协议：学术交流，传递html文本

        1. tcp建立连接
        2. GET / index.html
        3. 服务器返回html文件   以ASCII字符流返回
        4. 断开连接

    - 特点
        1. 只有请求行，没有请求头和请求体
        2. 服务器没有响应头，直接返回数据就可以
        3. 内容都是以ASCII字符流来传输

# HTTP/1.0
    - 因为浏览器诞生了，支持多类型的文件下载（html，css，js，图片，音频，视频），
      于是HTTP就不得不支持不同类型文件的下载

    - 如何实现多种类型文件的下载？
        1. 引入请求头和响应头，key-value
        2. HTTP发请求时会带上请求头信息，服务器返回数据时，会先返回响应头信息

    - 请求头和响应头是如何工作的
        1. 浏览器要知道服务器返回的类型
        2. 浏览器要知道服务器返回的数据压缩方式
        3. 浏览器要知道服务器要知道文件的编码方式

    请求头： accept: text/html
            accept-encoding: gzip, deflate, br
            accept-Charset: ISO-8859-1,utf-8
            accept-Language: zh-CN, zh 

    响应头：
            content-encoding: br
            content-type: text/html; charset=utf-8

            status: 200
            cache机制 
            content-length: 901

# HTTP/1.1（缝缝补补）
    - 1.0
        建立连接 -- HTTP请求 HTTP响应 -- 断开连接
        建立连接 -- HTTP请求 HTTP响应 -- 断开连接
        建立连接 -- HTTP请求 HTTP响应 -- 断开连接
        ...

    - 1.1
        1. 持久化连接：建立一个TCP连接可以进行多个HTTP请求
                 -- HTTP请求1 HTTP响应1 -- 
                 -- HTTP请求2 HTTP响应2 -- 
         建立连接 -- HTTP请求3 HTTP响应3 -- 断开连接
                 -- HTTP请求4 HTTP响应4 -- 
                 -- HTTP请求5 HTTP响应5 -- 

        请求头：Connection：close（不启用持久连接）

    - 队头阻塞

    - 虚拟机技术
        请求头：Host: xxxx

    - 服务端动态生成的内容（ejs...）
        content-length: xxx  无法描述文件的大小了

        所以引入了 Chunk transfer 机制， 将数据分割成若干个数据块，每个数据块上标记数据块的长度，
        最后发送了一个空数据块来告诉浏览器数据传输完毕

    - Cookie

# HTTP/2.0
    - 1.1 的优化：
        1. 增加了持久化连接
        2. 浏览器可以同时维护6个TCP连接
        3. 使用了CDN实现域名分片

    - 1.1 的主要问题
        1. 对带宽的利用率很低
            - TCP 慢启动
            - 同时开启多条TCP连接会竞争固定带宽
            - 队头阻塞问题

    - 2.0   多路复用
        1. 一个域名只使用一个TCP的长连接
        2. 资源并行请求

        - 二进制分帧层
    
    - 可以设置请求的优先级

    - 服务器推送
        当服务器给客户端返回一个html文件后，服务器自己知道该html中需要哪几份js和css，
        那么服务器就提前准备好这些js和css并且一并将js，css发送给浏览器

    - 头部压缩
        请求头和响应头

# HTTP/3.0
    - 2.0 的缺陷
        1. TCP的队头阻塞：因为TCP的传输是有序的，单个数据包丢失会造成阻塞
        2. TCP建立连接的延时：TCP握手，HTTPS中的TLS加密过程也有一次握手

    - 改进TCP协议
        TCP僵化，实现不可能
        1. 太多中间设备基于TCP生产，路由器，交换机...
        2. 操作系统也是内核也是基于TCP来工作

    - QUIC协议  （UDP升级）
        1. 有多路复用
        2. 传输可靠

    - 面临的挑战
        1. 浏览器和服务器都要升级支持QUIC协议
        2. 系统对UDP的优化很低，对TCP的优化很高
        3. 中间设备僵化







