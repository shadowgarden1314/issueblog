**1.部署 Cloudflare Pages在线测速：**

在 Cloudflare Pages 控制台中创建一个新的 Pages容器。
将 [CF-Workers-SpeedTestURL-main.zip](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/CF-Workers-SpeedTestURL-main.zip) 下载并上传到该容器中。
上传完成后就完成了自建测速地址，Cloudflare Pages容器域名地址就是测速地址；
可下载[Speed-tloos-main.zip](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/Speed-tloos-main.zip) 并将其解压到本地电脑中，修改测速代码中的-url https：//选项为自己搭建的测速地址。
测速代码：

CloudflareST.exe -tp 443 -f ip.txt -n 200 -dn 10 -sl 5 -url https：//
-tp 443 指定测速端口可改为上方可选端口
-f ip.txt 这是文件里的那个ip库，用来测速的，你自己有ip库可替换，无就不用管
-n 200 延迟测速线程；越多延迟测速越快，性能弱的设备，请勿太高；(默认 200 最多 1000)
-dn 10 下载测速时间；单个 IP 下载测速最长时间，不能太短；(默认 10 秒)
-sl 5 下载速度下限；只输出高于指定下载速度的 IP。

**2. 部署在线文本储存器：**
在 Cloudflare Wokers和Pages 控制台中创建一个KV空间容器后返回Cloudflare Wokers和Pages 控制台。

在Cloudflare Pages 控制台中创建一个新的 Pages容器，将 [CF-Workers-TEXT2KV-main.zip](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/CF-Workers-TEXT2KV-main.zip) 下载并上传到该容器中。

上传完成后需到该容器设置/函数中绑定前面创建的KV容器；

绑定KV容器后在创建的Pages容器中选择设置/环境变量添加以下变量：

变量名称：TOKEN

值：访问在线文本储存器的密码

变量添加完成后再次回到该项目部署页面，再次上传该资产文件 [CF-Workers-TEXT2KV-main.zip](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/CF-Workers-TEXT2KV-main.zip)

**3. 部署节点订阅器：**
在 Cloudflare Wokers和Pages 控制台中创建一个Wokers容器。

删除Wokers原有代码，将 [_worker.js](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/_worker.js) 中的代码粘贴到该容器内并部署。

部署完成后需到该容器设置/变量中添加以下变量；

变量名称：HOST

值：之前通过Pages搭建的订阅的域名；

变量名称：UUID

值：之前通过Pages搭建的订阅时所使用的UUID；

变量名称：PATH

值：之前通过Pages搭建的订阅时所使用的PATH；







※  搭建测速上传Cloudflare Pages 资产下载：[点击下载](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/CF-Workers-SpeedTestURL-main.zip)

※  本地测速压缩包下载：[点击下载](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/Speed-tloos-main.zip)


※  搭建在线文本储存器资产下载：[点击下载](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/CF-Workers-TEXT2KV-main.zip)

※  搭建节点订阅器代码：[点击进入](https://github.com/Onezyh/SpeedST-Vless-TXT-USB/blob/mian/_worker.js)

※  本期视频演示教学：https://youtu.be/4U6N2DeZC4k