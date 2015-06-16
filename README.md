YAWebServer(可通过php-fpm解析php)
==============================

##依赖
- [ahttpd](https://github.com/lucklove/ahttpd)

##编译(先安装[ahttpd](https://github.com/lucklove/ahttpd))
- cd YAWebServer
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

##注意
  php-fpm要求doc_root的各级目录都至少可读，所以访问放在/home/user及其子孙目录下的php文件时可能报404,  
因为php-fpm默认以apache这个用户启动，而/home/user的目录权限默认为700，apache对该级目录没有读权限.
