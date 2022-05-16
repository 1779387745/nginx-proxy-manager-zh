
[Original English README](https://github.com/xiaoxinpro/nginx-proxy-manager-zh/blob/develop-zh/README-en.md)

<p align="center">
    <img src="https://nginxproxymanager.com/github.png">
    <br>
</p>

本项目是基于 [NginxProxyManager/nginx-proxy-manager](https://github.com/NginxProxyManager/nginx-proxy-manager) 翻译的中文版本，该项目属于一个预构建的docker映像，它可以让你轻松地部署到你的网站上运行，包括免费的SSL，而不需要知道太多关于 Nginx 或 Let's Encrypt 的信息。  

![](http://image.xiaoxin.pro/2022/05/16/75687b5bfffbe.png)

## 快速部署

1. 安装Docker和Docker-compose

- [Docker官方安装文档（英文）](https://docs.docker.com/install/)
- [Docker-Compose官方安装文档（英文）](https://docs.docker.com/compose/install/)
- **[Docker和Docker-compose安装文档（中文）](https://blog.csdn.net/zhangzejin3883/article/details/124778945)**

2. 创建一个 `docker-compose.yml` 文件:

```yml
version: '3'
services:
  app:
    image: 'chishin/nginx-proxy-manager-zh:latest'
    restart: always
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
```

3. 部署运行

```bash
docker-compose up -d
```

4. 登录管理页面

当你的docker容器成功运行，使用浏览器访问`81`端口。
有些时候需要稍等一段时间。

[http://127.0.0.1:81](http://127.0.0.1:81)

默认管理员信息:
```
Email:    admin@example.com
Password: changeme
```

使用这个默认用户登录后，系统会立即要求您修改详细信息和密码。

5. 快速升级

```bash
docker-compose pull
docker-compose up -d
```

这个项目将自动更新任何数据库或其他要求，所以你不必遵循任何疯狂的指示。上面的这些步骤将提取最新的更新并重新创建docker容器。

## 更多

关于本应用的更多用法请访问官方文档：

- [项目源码](https://github.com/NginxProxyManager/nginx-proxy-manager)
- [项目官网](https://nginxproxymanager.com/)
- [安装手册](https://nginxproxymanager.com/setup/)
- [高级配置](https://nginxproxymanager.com/advanced-config/#best-practice-use-a-docker-network)
- [常见问题](https://nginxproxymanager.com/faq/#do-i-have-to-use-docker)

## 捐赠

如果您觉得本项目对你有帮助，欢迎给予我们一定的捐助来翻译项目的长期发展。

### 支付宝扫码捐赠

![支付宝扫码捐赠](https://github.com/xiaoxinpro/xxjzWeb/blob/master/Public/Home/i/alipay.png)

### 微信扫描捐赠

![微信扫描捐赠](https://github.com/xiaoxinpro/xxjzWeb/blob/master/Public/Home/i/wechat.png)
