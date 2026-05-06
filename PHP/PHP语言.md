# PHP语言



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





