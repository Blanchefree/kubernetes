
The open source operation platform : CMDB, project deploy, Crontab, DevOps , Monitor.
 
开源DevOps平台：资产管理、定时任务、项目部署、自动运维、系统监控

开发环境
centos 7.2(1511) django 1.9.8 python 2.7

服务端安装
git clone https://github.com/

执行安装脚本

adminset/install/server_install.sh
安装过程需要输入管理员数据库等交互信息

客户端说明
说明：为保证注册IP是管理IP（后续会被ansible等调用），客户端的IP抓取目前使用主机名解析，也就是说主机名必须可以被解析才能执行自动上报脚本，否则报错。 如：主机名为centos6 请在/etc/hosts中加入相应的解析 192.168.x.x centos6，这样再执行agent_post_info.py 可以保证正常运行。 centos7不进行解析也可获取主机IP，centos6必须在/etc/hosts对主机名进行解析。

step1:
yum install -y smartmontools 
yum install -y dmidecode

step2:
在客户机上执行 scripts/agent_post_info.py 文件自动上报主机信息

访问
http://your_server_ip

使用自己在安装过程中创建的super admin用户名密码

使用说明
请转到：使用说明

dashboard

安全
建议不要将程序启动在有公网可以直接访问的设备上，如果需要请使用VPN。
建议生产环境中使用https配置服务器
由于开发方便，在django的settings中开启了DEBUG，在生产中需要关闭并指定自己的域名。
