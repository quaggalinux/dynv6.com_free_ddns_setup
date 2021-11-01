# dynv6.com_free_ddns_setup
配置dynv6.com免费动态域名解析服务的方法，包括动态域名的ipv4及ipv6地址更新  
 
最近发现了一个比较好用的免费ddns服务提供商dynv6.com，给各位童鞋分享一下它的配置方法

dynv6.com的免费帐号更新TTL为60秒，更新非常非常快

注册dynv6.com的免费帐号只需要一个邮箱

登录进去后点 My Zones 可以增加ddns域名或修改已经有的ddns域名，点右上角的用户名可以出菜单，
点 keys 可以重新生成或拷贝用于更新ip的URL密码(token)

除了使用dynv6.com提供的ddns域名，你也可以迁入自己在其他域名注册商已经注册的域名，然后做ddns更新

下面是更新ipv4的URL，如果ipv4项写auto的话，缺省使用现在被ipv4.dynv6.com网页检测到的出口ipv4地址进行更新，
当然也可以写确定的ip地址或变量名

zone字段可以写成hostname或Hostname，URL必须有""符号包裹否则报告token missing！！！！！！！！！

curl -s "https://ipv4.dynv6.com/api/update?zone=yourdomain.v6.navy&ipv4=auto&token=bupdW36PFTUAyKyx6ho8R2hsKyzEUd"

curl -s "https://ipv4.dynv6.com/api/update?hostname=yourdomain.v6.navy&ipv4=1.1.1.1&token=bupdW36PFTUAyKyx6ho8R2hsKyzEUd"

curl -s "https://ipv4.dynv6.com/api/update?hostname=yourdomain.v6.navy&ipv4=$NEWIP&token=bupdW36PFTUAyKyx6ho8R2hsKyzEUd"

如果是梅林固件必须用下面的连接更新，-k参数是不检验证书

curl -s -k "https://ipv4.dynv6.com/api/update?zone=yourdomain.v6.navy&ipv4=auto&token=bupdW36PFTUAyKyx6ho8R2hsKyzEUd"

下面是更新ipv6地址的URL命令，ipv6.dynv6.com网页必须是主机具有公网ipv6地址才能访问，因为这时要更新的不是路由器出口的ipv6地址，而是主机的ipv6地址，如果ipv6项写auto的话，缺省使用现在被ipv6.dynv6.com网页检测到的主机的ipv6公网地址进行更新，当然也可以写确定的ipv6地址或变量名

curl -s "https://ipv6.dynv6.com/api/update?zone=yourdomain.v6.navy&ipv6=auto&token=bupdW36PFTUAyKyx6ho8R2hsKyzEUd"  
  
   
     
