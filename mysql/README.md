# Docker 安装mysql

## https://hub.docker.com/_/mysql/

## 命令
```
sudo docker rm -f moe-mysql
sudo docker run --restart=always --name moe-mysql -v /data/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql
```

## 连接本地容器 mysql
```
sudo docker run -it --link moe-mysql:mysql --rm mysql sh -c 'exec mysql -h"$MYSQL_PORT_3306_TCP_ADDR" -P"$MYSQL_PORT_3306_TCP_PORT" -uroot -p"$MYSQL_ENV_MYSQL_ROOT_PASSWORD"'

```

## 连接远程 mysql
```
sudo docker run -it  --rm mysql sh -c 'exec mysql -h  -P  -uroot -p '

```

## mysql系统命令

+ 查看当前系统版本(lsb_release -a)

+ 重启mysql
```
/etc/init.d/mysql stop   
/etc/init.d/mysql start
```