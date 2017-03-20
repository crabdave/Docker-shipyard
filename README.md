# Docker-shipyard

参考：https://shipyard-project.com/

```
vim /etc/sysconfig/docker
OPTIONS= 中添加-H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock 
systemctl restart docker.service
```

```
msg="Error creating connection: gorethink: dial tcp 172.17.0.2:28015: getsockopt: connection refused" 
rethinkdb启动比较慢，得等会
```

-系统启动有些慢，得等会再才能打开登录页面，之后的登录也比较慢
-登录shipyard界面
-现在可以访问http://<your-host-ip>:8080来登录shipyard了，默认用户名/密码是：admin/shipyard。

