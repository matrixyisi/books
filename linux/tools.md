## 常用工具软件包

1. net-tools (base)
2. git2u (ius)
3. subversion (centos/updates)

## nmcli

|描述|命令|
|----|----|
|查看所有设备|nmcli d|
|查看所有连接|nmcli c|
|查看static这个连接|nmcli c show static|
|添加dhcp连接|nmcli c add con-name dhcp type ethernet ifname enp0s3|
|添加static连接|nmcli c add con-name static type ethernet ifname enp0s3 ip4 192.168.56.20/24 gw4 192.168.56.1|
|修改连接属性，参考show属性|nmcli c mod static ipv4.addresses 192.168.56.20/24|
|启动static连接|nmcli c up static|
|关闭static连接|nmcli c down static|

## netstat

netstat 是一款命令行工具，可用于列出系统上所有的网络套接字连接情况，包括 tcp, udp 以及 unix 套接字，另外它还能列出处于监听状态（即等待接入请求）的套接字。

|描述|命令|
|----|----|
|列出所有|netstat -a|
|列出tcp|netstat -at|
|列出udp|netstat -au|
|禁用域名解析|netstat -ant|
|*监听中的连接|netstat -ntl|
|获取进程名|netstat -ntlp|
|获取进程用户|netstat -ntlpe|
|获取内核路由|netstat -nr|

## virtualbox

virtualbox采用nat+hostonly模式, nat用来上网, hostonly用来构建内部网络.
centos按照顺序加载网卡配置文件, 所以先配置nat后配置hostonly的话，hostonly不要写网关, 否则会覆盖掉nat.
TODO: 先配置hostonly后配置nat.