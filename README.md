#GoBlog

基于Go语言和beego框架的简易博客系统

#版权说明

该版本fork自[http://www.lisijie.org/](http://www.lisijie.org/)

由于Go语言包的原因fork后再git,再编译时会产生包路径问题

#修改内容：


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

