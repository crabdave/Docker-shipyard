# Docker-shipyard

##参考：https://shipyard-project.com/

##修改Docker配置
```
vim /etc/sysconfig/docker
OPTIONS= 中添加-H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock 
systemctl restart docker.service
```


##出现些小问题
```
msg="Error creating connection: gorethink: dial tcp 172.17.0.2:28015: getsockopt: connection refused" 
ERROR: for shipyard-shipyard  Cannot create container for service shipyard-shipyard: Could not get container for shipyard-rethinkdb
ERROR: for shipyard-agent  Cannot create container for service shipyard-agent: Could not get container for shipyard-discovery
ERROR: for shipyard-swarm  Cannot create container for service shipyard-swarm: Could not get container for shipyard-discovery
ERROR: Encountered errors while bringing up the project.
```

rethinkdb启动比较慢，得等会,有些容器启动比较慢现出异常多重启几次（docker-compose up -d）

shipyard-swarm-agent 启动时join shipyard-proxy 有时候会出现问题，找到shipyard-proxy对应的容器IP再修改docker-compose.yml再启动就可以了

系统启动有些慢，得等会再才能打开登录页面，之后的登录也比较慢

登录shipyard界面

现在可以访问http://<your-host-ip>:8080来登录shipyard了，默认用户名/密码是：admin/shipyard。

