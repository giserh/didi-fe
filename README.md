didi-fe
=======

Something of didi frontend

*写在前面*
>关于svn、开发环境、测试环境、线上路径、访问路径、域名之间的对应关系进行记录，希望Team内同学对这些路径熟记于心，在工作中能够快速找到对应的资源以提高效率。

###MVC模式
*写这段的目的是帮助大家更好的理解前后台是怎么协调的*
1. MVC开发模式－－M（Model）C（Controller）V（View）。
2. 两个分离－－数据M和行为C分离，行为C和表现V分离，V就是FE的一亩三分地。
3. MVC跟传统的asp、jsp、php最大的不同就在于，以往用户请求都是直接请求一个文件，而MVC请求的是action，action是Controller中的方法比如我们访问`http://test.diditaxi.com.cn/api/v2/weixinapi` `weixinapi`就是一个Controller对应着controllers文件夹下的`weixinapi.php`。
4. `weixinapi.php`里面有一个`function index`，index方法就是Controller的默认方法，这个index内部需要load->(home.html)，执行完load方法后，正常情况下就response了`home.html`
5. `home.html`里面如`/static/webapp/didi.min.js`等代码，浏览器会再次发起请求，这个时候就是请求**静态资源**了如`http://test.diditaxi.com.cn/static/webapp/didi.min.js`这些资源在静>态目录下的`/static/...`下

*PS：想了解更详细的细节请再沟通*

###113服务器
`xiaoju@113.11.197.199 端口22 密码请找相关的人取`
静态路径：`/home/xiaoju/webroot/` 可以建立自己的静态路径如jb
访问路径：http://113.11.197.199/jb/example.html
项目路径：`/home/xiaoju/app/api/v2`v2下面有models，controllers，views就是MVC。
访问路径：`http://113.11.197.199/api/v2/weixinapi`


###118服务器--曾经的218
`xiaoju@118.244.193.242 端口22 密码请找相关的人取`这个IP绑定的域名是`http://test.diditaxi.com.cn`
静态路径：/home/xiaoju/developers/ 可以建立自己的静态路径如jb
访问路径：http://test.diditaxi.com.cn/jb/example.html
项目路径：`/home/xiaoju/developers/hongbao/api/v2`这个hongbao被重定向到了api/v2/也就是说http://test.diditaxi.com.cn/hongbao/api/v2/weixinapi跟http://test.diditaxi.com.cn/api/v2/

##vpn
1. 先找OP申请vpn，然后登录`http://vpn.xiaojukeji.com:8000`上面有使用说明以及需要的证书软件
2. vpn的作用是让我们在家里也能通过`svn://10.10.10.60/xiaoju/server`来访问svn服务。

##svn路径
1. 安装好vpn方便我们随时随地的使用svn，当然在`937wifi`或者`113，218服务器`上开发时使用`svn://118.244.193.172/xiaoju/server/`就不需要了vpn了。
2. 前端同学svn中的路径有4个
    - `svn://10.10.10.60/xiaoju/server/static/` 静态资源目录，跟线上一致
    - `svn://10.10.10.60/xiaoju/server/share/` 运营活动相关的静态页面，跟线上一致
    - `svn://10.10.10.60/xiaoju/server/frontend/` 前端同学特有的路径，用来做前端知识积累使用，跟具体项目无关
    - 其他的具体项目比如微信的主干`svn://10.10.10.60/xiaoju/server/api/v2/trunk/views/webapp`已被废弃
"开发环境相关.md" [noeol] 97L, 5479C

