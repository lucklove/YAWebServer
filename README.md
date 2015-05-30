WebServer(可通过php-fpm解析php)
==============================

##依赖
- [ahttpd](https://github.com/lucklove/ahttpd)

##编译
- cd WebServer
- mkdir build
- cd build
- cmake ..
- make

##php-fpm配置
###安装
  大多数linux发行版的仓库中都有php-fpm,通过包管理工具即可安装, 比如   
archlinux(`sudo pacman -S php-fpm`), centos(`sudo yum install php-fpm`).
###配置
- 修改php-fpm.conf, 添加listen = 127.0.0.1:9000.
- 修改php.ini, 注释掉doc_root = xxx.

##运行
- sudo php-fpm(optional)
- ./WebServer doc_root(doc_root必须为绝对路径)
