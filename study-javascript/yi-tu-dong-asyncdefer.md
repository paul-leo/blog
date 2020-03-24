# &lt;script&gt;的加载与执行顺序

**defer :**立即下载但延迟执行，两个延迟脚本的执行顺序任然是**按照先后顺序执行**，**延迟脚本会先于DOMContentLoaded**

**async:** 异步脚本，**谁先下载完谁先执行**，所以最好相互直接没有依赖，**不一定先于DOMContentLoaded**

![](../.gitbook/assets/2151798436-59da4801c6772_articlex.png)



