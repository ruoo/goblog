#GoBlog

基于Go语言和beego框架的简易博客系统

#版权说明

该版本fork自[github.com/lisijie/goblog](http://github.com/lisijie/goblog/)

由于Go语言包的原因fork后再git,再编译时会产生包路径问题

#修改内容：
* 评论改为多说系统
* 左侧面板删除hover效果
* 增加Tag列表,tag文章列表
* 修改归档tag链接
* 修改日期格式

##编译安装说明：

设置GOPATH(安装目录)

	$ export GOPATH=/path/to/goblog
	$ cd /path/to/goblog

获取源代码，下载完成后会自动编译为goblog可执行文件
	
	$ go get github.com/ruoo/goblog

配置修改(conf/app.conf)

	appname = goblog
	httpport = 8080
	runmode = dev
	dbhost = localhost 
	dbport = 3306
	dbuser = root
	dbpassword = 123456
	dbname = goblog
	dbprefix = tb_

导入MySQL

	$ mysql -u username -p -D goblog < goblog.sql

运行
	
	$ ./goblog
	或
	$ nohup ./goblog 2>&1 > goblog.log &
	设为后台运行

访问： 

http://localhost:8080

后台地址：

http://localhost:8080/admin

帐号：admin
密码：admin888

## Nginx配置
        server{
       	listen 80;
               server_name ruoo.whosenet.com;
       	charset utf-8;

       	location / {
       			proxy_set_header X-Forwarded-For $remote_addr;
       			proxy_set_header Host            $http_host;
       			proxy_pass http://127.0.0.1:8070;
       		}

       	}

