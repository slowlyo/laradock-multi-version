# Laradock Multi Version

让 Laradock 支持多版本 PHP 同时运行

## 特性

- 支持多个 PHP 版本同时运行
- 不影响 Laradock 更新 (只改动了 Laradock 原有的一个文件)

## 快速开始

### 1. 安装

将本项目克隆到你的 Laradock 根目录:

```shell
git clone git@github.com:slowlyo/laradock-multi-version.git {你的 Laradock 目录}/.laradock-multi-version
```

### 2. 配置

在 Laradock 的 `docker-compose.yml` 文件中添加以下配置:

```yml
# 注意: 需要放在 Laradock docker-compose.yml 文件的第一行
include:
  - .laradock-multi-version/docker-compose.yml
```

### 3. 启动服务

使用 docker compose 命令启动需要的服务:

```shell
# 示例: 启动 PHP 7.4、PHP 8.0 
# 在 Laradock 目录下执行
docker compose up -d php-fpm-74 workspace-74 php-fpm-80 workspace-80 ...
```

### 4. 使用多版本 PHP

```diff
location ~ \.php$ {
    # ...
-   fastcgi_pass php-fpm:9000;
+   fastcgi_pass php-fpm-80:9000;
    # ...
}
```