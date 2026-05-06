# PHP语言



## 常用命令

| 命令                                            | 说明                                                  |
| ----------------------------------------------- | ----------------------------------------------------- |
| php -i \| grep php.ini  / php --ini             | 查看PHP加载的配置文件                                 |
| php -i \| grep extension_dir                    | 查看加载的php扩展目录                                 |
| php -i  \| grep configure                       | 查看编译时参数                                        |
|                                                 |                                                       |
| kill -USR2 16550                                | 平滑重启php-fpm (这里的16550是进程号)                 |
| kill -USR2 `cat /usr/local/var/run/php-fpm.pid` | USR2 平滑重启所有worker进程并重新载入配置和二进制模块 |
|                                                 |                                                       |
|                                                 |                                                       |
|                                                 |                                                       |
|                                                 |                                                       |
|                                                 |                                                       |





## 开发技巧

#### 端口映射

> 当远程服务无法通过代码直连到相应的服务端口,但是可以通过代理访问的情况下
>
> 可以将远程端口映射到本地进行使用

```bash
# 连接开发环境Redis:
ssh -i C:\Users\EDY\.ssh\id_rsa -L 6380:127.0.0.1:6379 root@xxx.xx.xxx.xxx -N

# 连接开发环境MySQL：
ssh -i C:\Users\EDY\.ssh\id_rsa -L 3307:127.0.0.1:3306 root@xxx.xx.xxx.xxx -N

## 参数说明
### -i: 指定使用的私钥文件路径
### -L: 进行本地端口转发
### -N: 仅建立转发，不执行远程命令，不会打开远程 shell
### 3307:127.0.0.1:3306 将本地3307端口映射到远程的127.0.0.1:3306上
### root@xxx.xx.xxx.xxx 指定登录服务的用户名@IP

```





## 环境搭建

### Herd

> 官网: https://herd.laravel.com

#### [Windows]

##### 安装&下载

1. 访问https://herd.laravel.com/windows,并下载安装程序
2. 一般安装完成的路径:C:\Users\用户名\.config\herd\bin\php83\php.exe

##### 常用命令

| 命令             | 作用                                    |
| ---------------- | --------------------------------------- |
| herd start       | 启动 Herd 服务                          |
| herd stop        | 停止 Herd 服务                          |
| herd restart     | 重启 Herd 服务                          |
| herd link        | 将当前目录链接为站点                    |
| herd unlink      | 移除当前站点的链接                      |
| herd secure      | 为当前站点启用 HTTPS                    |
| herd unsecure    | 禁用 HTTPS                              |
| herd open        | 在浏览器中打开当前站点                  |
| herd edit        | 用默认 IDE 打开当前站点                 |
| herd use php@8.2 | 切换当前站点的 PHP 版本                 |
| herd php artisan | 运行 artisan 命令（替代 `php artisan`） |

> 💡 **小技巧**：使用 `herd php` 而不是直接 `php` 来运行命令，可以确保使用 Herd 管理的 PHP 版本，避免与系统 PHP 冲突





## Composer

### 常用命令

| 命令                                                         | 说明                          |
| ------------------------------------------------------------ | ----------------------------- |
| composer install                                             | 根据composer.json文件安装依赖 |
| composer require 包名称                                      | 安装单独依赖包                |
| composer config -gl                                          | 查看镜像源                    |
| composer config -g --unset repos.packagist                   | 取消全局配置                  |
| composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/ | 全局配置镜像源                |
| composer config repo.packagist composer https://mirrors.aliyun.com/composer/ | 本地配置镜像源                |
|                                                              |                               |
|                                                              |                               |
|                                                              |                               |
|                                                              |                               |
|                                                              |                               |

### 镜像源加速

```bash
# 腾讯云(推荐)
composer config -g repos.packagist composer https://mirrors.cloud.tencent.com/composer/
# 阿里云
composer config -g repos.packagist composer https://mirrors.aliyun.com/composer/
# 华为云
composer config -g repos.packagist composer https://repo.huaweicloud.com/repository/php/
# 国内镜像
composer config -g repos.packagist composer https://packagist.phpcomposer.com
# 交通大学
composer config -g repos.packagist composer https://packagist.mirrors.sjtug.sjtu.edu.cn
```





## 第三方包





### barryvdh/laravel-ide-helper - Laravel 开发工具包

```bash
// 1.安装插件 
composer require --dev barryvdh/laravel-ide-helper
// 2.生成Laravel Facade文档
php artisan ide-helper:generate
// 3. 为数据模型生成注释
php artisan ide-helper:model
// 4. 生成PHPStorm Meta文件
php artisan ide-helper:meta
```



###  reliese/laravel - Laravel 代码生成工具

```
// 1.安装插件
composer require reliese/laravel --dev
// 2.生成config/models.php配置文件
php artisan vendor:publish --tag=reliese-models
// 3.根据表生成Model文件
php artisan code:models
// 3.1 指定表名
php artisan code:models --table=表名
```





