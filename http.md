Hypertext Transfer Protocol   超文本传输协议，应用层协议，基于文本，没有使用二进制格式

过程：解析url，获取主机名\(dns转换为ip\)、port，与服务器建立tcp连接，发送请求报文、接受响应报文，关闭连接。

http:// （scheme）      www.baidu.com（网站）      /specials/a.gif（资源）

MIME：text/html\(html格式的文本\)   text/plain\(普通的ASCII文本\)  image/jpeg

------------------------------------------URL

有些需要用户密码认证，如`ftp:user:pwd@//10.128.158.15/app_class/conf.properties`

url编码：采用ASCII编码格式传输，就是将一些特殊的字符、中文  用%+两位16进制ASCII        eg：空格   -----》  %20

将中文编码为16进制的ASCII时，可以是utf-8,也可以是gb2312等

-------------------------------------------http连接，由tcp/ip协议承载

![](/assets/https.PNG)

http传送一条报文时，会以流的形式将报文数据通过一条打开的tcp连接按序传输，tcp接受到流后，会将流分成段的小数据块，并将段封装在ip分组中。

http处理过程中的网络时延：

![](/assets/http时延.PNG)

提高http性能：
+ 并行连接：消耗内存，对带宽有要求
+ 持久连接：http1.0+ http事务结束后，对tcp连接持久化,不用每次建立连接。
Connection:keep-alive,需要请求时带上它用于激活。
http1.1用persisitent connection替代了keep,默认是持久化的，若不用持久化，需要标明Connection:close

    
+ 管道化连接

keep-alive 与哑代理，代理不认识keep-alive的含义，并且在client与server之间传输，但是当client再次与代理用这个ka连接发起请求时，会在client被挂起，直到client超时将其关闭


