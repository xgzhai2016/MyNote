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

常见的tcp时延：

TCP连接建立握手，TCP慢启动拥塞控制，数据聚集Nagle算法，用于捎带确认的tcp延迟确认算法，TIME\_WAIT时延和端口耗尽。小的http事务在tcp建立上会花费50%的时间

























































































































