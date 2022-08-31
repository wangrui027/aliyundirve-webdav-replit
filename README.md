## 阿里云盘 webdav replit 部署程序

## 程序说明

本程序将 [aliyundrive-webdav](https://github.com/messense/aliyundrive-webdav) 部署于 [replit.com](https://replit.com/) 实现阿里云盘文件的快速查看及下载。



点击下面的按钮进行快速部署

[![](run-on-replit.svg)](https://repl.it/github/wangrui027/aliyundirve-webdav-replit)

点击按钮运行应用后第一次运行必然报错：

>`Nix channel was not detected in your imported .replit file but is required for all Nix Repls. The latest stable Nix channel "[object Object]" was automatically added to your .replit file.

尝试手动添加正确的 `REFRESH_TOKEN` 环境变量后解决问题，但本质原因还没弄清楚，了解的同学感谢指正



为降低 webdav 使用复杂度，程序仅对 `aliyundrive-webdav` 程序的核心功能提供配置，具体如下：

- 支持 `aliyundrive-webdav` 程序版本的指定
- 支持云盘根路径指定
- 支持设置文件是否只读
- 支持账号密码配置
- 支持目录索引的开启或关闭
- 将目录缓存过期时间设置为 60 秒

## 使用场景

**1、个人或团队共享文件：**

不设置文件只读、开启账号密码

**2、作为开放的文件分发服务：**

设置文件只读、关闭账号密码

**3、作为图床服务：**

设置文件只读、关闭账号密码、关闭目录索引

## 程序配置

| 密钥名称       | 必选 | 密钥说明                                                     |
| -------------- | ---- | ------------------------------------------------------------ |
| REFRESH_TOKEN  | 是   | 阿里云盘的 refresh token                                     |
| WEBDAV_VERSION | 否   | aliyundrive-webdav 程序的版本号，如：v1.10.1、v1.10.0 等具体的版本号 |
| ROOT_DIR       | 否   | webdav 根目录对应的网盘路径，[默认值：/]                     |
| READ_ONLY      | 否   | webdav 是否只读，随便传一个值，或不传                        |
| AUTH_USER      | 否   | webdav 访问账户                                              |
| AUTH_PASSWORD  | 否   | webdav 访问密码                                              |
| AUTO_INDEX     | 否   | webdav 是否开启目录索引，随便传一个值，或不传，默认启用      |

