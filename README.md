# Docker部署Nginx/PHP基础环境
在项目中部署基础服务：Nginx&PHP

本地开发部署使用：[dnmp](https://github.com/yeszao/dnmp)

# 目录结构
    /
    ├── data                        数据库数据目录
    |—— composer                    composer 全局
    ├── services                    服务构建文件和配置文件目录
    │   ├── nginx                   Nginx 配置文件目录
    │   ├── php                     PHP5.6 - PHP7.3 配置目录
    ├── logs                        日志目录
    ├── docker-compose.sample.yml   Docker 服务配置示例文件
    ├── env.smaple                  环境配置示例文件


# 开始使用
    $ cd mydnmp                                         # 进入项目目录
    $ cp env.sample .env                                # 复制环境变量文件
    $ cp docker-compose.sample.yml docker-compose.yml   # 复制 docker-compose 配置文件
    $ docker compose up                                 # 启动
    $ docker compose down                               # 关闭

**tips：docker compose up -d php             # 指定执行php服务**

修改项目路径：

![](https://paper-attachments.dropbox.com/s_D1F091C2EB950C41C2CB4FE4E3803F3A8B8E42DC5DB4FE3022F31FFC1F8CA283_1627004568672_image.png)


SOURCE_DIR 设置到项目路径




执行magento命令需要进入容器后才能执行

    $ docker exec -it php sh
    $ bin/magento setup:upgrade

[PHP NGINX 调优](https://blog.panghu.info/modern-php/optimization/)
我们应该使用克里斯.科耐特开发的[PHP Iniscan工具](https://github.com/psecio/iniscan)扫描php.ini文件，检查是否使用了安全方面的最佳实践。
[PHP FPM 配置](https://blog.panghu.info/modern-php/php-fpm/)

待续：opcache配置分离| xhprof部署(线上环境xdebug开销太大)

