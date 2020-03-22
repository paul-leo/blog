# 利用Electron实现tinypng的客户端

tinypng ,也就是熊猫压缩是很多前端喜欢的压缩工具，官方提供了网站版，需要手动上传和下载图片，并且对于张数有限制，再使用的过程中有些繁琐，当然官方有提供nodejs的api版本，但是也有诸多限制。

 看到网上有人用nodejs写了一段自动上传并压缩的代码，原文再下面

{% embed url="https://segmentfault.com/a/1190000015467084" %}

 思路和原文没什么不同，只是我再原来的基础上

1. 加入了随机ip绕过20张限制，
2. 封装成了nodejs的接口，方便集成到脚手架中和在Electron中使用

修改后的大致思路是这样的。

* 递归获取本地文件夹里的文件
* 过滤文件，格式必须是`.jpg` `.png`,大小小于5MB.\(文件夹递归\)
* ~~每次只处理一个文件（可以绕过20个的数量限制）~~
* **每一次随机一个IP地址并且同步进行（提升压缩速度，绕过20张数量限制）**
* 处理返回数据拿到远程优化图片地址
* 取回图片更新本地图片

 贴上nodejsAPI 版的Github地址

{% embed url="https://github.com/focusbe/tinypngjs" %}

再有了上面nodejs的版本后，再通过Electron就可以打包成客户端的形式，如果在不集成到脚手架的情况下也可以享受更加便利的压缩图片。  
  
同样也贴上客户端版的Gihub地址

{% embed url="https://github.com/focusbe/tinyImage" %}



 



