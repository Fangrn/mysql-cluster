# mysql-cluster


1，先  docker-compose build 打包镜像
2，运行集群 docker-compose up db-cluster-1 db-cluster-2 db-cluster-3 &
3，运行一个临时的mysql-router,目的通过mysql-shell建立集群 docker-compose run db-mysql-router /bin/bash
运行mysqlsh，执行以下脚本mysql-shell.script
4,启动mysql-router  docker-compose up db-mysql-router &
5，数据库测试，连接 6446 和6447 端口，SELECT * FROM `performance_schema`.replication_group_members;
