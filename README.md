
[Original English README](https://github.com/xiaoxinpro/nginx-proxy-manager-zh/blob/develop-zh/README-en.md)

<p align="center">
    <img src="https://nginxproxymanager.com/github.png">
    <br>
</p>

����Ŀ�ǻ��� [NginxProxyManager/nginx-proxy-manager](https://github.com/NginxProxyManager/nginx-proxy-manager) ��������İ汾������Ŀ����һ��Ԥ������dockerӳ���������������ɵز��������վ�����У�������ѵ�SSL��������Ҫ֪��̫����� Nginx �� Let's Encrypt ����Ϣ��  

![](http://image.xiaoxin.pro/2022/05/16/75687b5bfffbe.png)

## ���ٲ���

### 1. ��������

��װDocker��Docker-compose

- [Docker�ٷ���װ�ĵ���Ӣ�ģ�](https://docs.docker.com/install/)
- [Docker-Compose�ٷ���װ�ĵ���Ӣ�ģ�](https://docs.docker.com/compose/install/)
- **[Docker��Docker-compose��װ�ĵ������ģ�](https://blog.csdn.net/zhangzejin3883/article/details/124778945)**

### 2. ����YAML�ļ�

����һ�� `docker-compose.yml` �ļ�:

```yml
version: '3'
services:
  app:
    image: 'chishin/nginx-proxy-manager-zh:release'
    restart: always
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
```

### 3. ��������

```bash
docker-compose up -d
```

### 4. ��¼����ҳ��

�����docker�����ɹ����У�ʹ�����������`81`�˿ڡ�
��Щʱ����Ҫ�Ե�һ��ʱ�䡣

[http://127.0.0.1:81](http://127.0.0.1:81)

Ĭ�Ϲ���Ա��Ϣ:
```
Email:    admin@example.com
Password: changeme
```

ʹ�����Ĭ���û���¼��ϵͳ������Ҫ�����޸���ϸ��Ϣ�����롣

### 5. ��������

```bash
docker-compose down
docker-compose pull
docker-compose up -d
```

�����Ŀ���Զ������κ����ݿ������Ҫ�������㲻����ѭ�κη���ָʾ���������Щ���轫��ȡ���µĸ��²����´���docker������

## ����

### 1. �ٷ��ĵ���Ӣ�ģ�

���ڱ�Ӧ�õĸ����÷�����ʹٷ��ĵ���

- [��ĿԴ��](https://github.com/NginxProxyManager/nginx-proxy-manager)
- [��Ŀ����](https://nginxproxymanager.com/)
- [��װ�ֲ�](https://nginxproxymanager.com/setup/)
- [�߼�����](https://nginxproxymanager.com/advanced-config/#best-practice-use-a-docker-network)
- [��������](https://nginxproxymanager.com/faq/#do-i-have-to-use-docker)

### 2. �滻���ľ���

����ʹ�ùٷ�ʾ����`docker-compose`ʱ��Ҫע�⣬��image����`jc21/nginx-proxy-manager`�滻Ϊ`chishin/nginx-proxy-manager-zh`����ʵ�����Ĳ���

### 3. �������ľ���

���ľ���û�����¹�����˴��룬��[Dockerfile-zh](https://github.com/xiaoxinpro/nginx-proxy-manager-zh/blob/develop-zh/docker/Dockerfile-zh)�ļ����Ե�֪�����ľ�����ڹٷ������滻ǰ�˴�����ʵ�ֵģ��������İ汾��ȫ��������ٷ��汾��ȫ��ͬ��ֻ����ʾ��������ֲ�ͬ������

### 4. ����DNSPod����֤��ʧ��

��������2.9.19�汾��ʼ���Ѿ����ڣ�ԭ����`zope`����ģ�����ARM�ܹ�һֱ��װʧ�������޷�����������У�����ʹ�����·����޸������⣺

����ȷ��nginx-proxy-manager-zh��Docker�����Ѿ��������У�ʹ��`docker-compose ps`�鿴���������������������Ϊ`npm-zh`��

������������ע���滻�����е���������

```
docker exec -it npm-zh bash
```

ִ�а�װ`zope`���

```
python3 -m pip install --upgrade pip
pip install certbot-dns-dnspod
pip install zope
```

�ȴ���װ��ɣ��˳�������

```
exit
```

���ˢ����������ٴ�ʹ��DNSPod����֤�鼴�ɡ�

## ����

��������ñ���Ŀ�����а�������ӭ��������һ���ľ�����������Ŀ�ĳ��ڷ�չ��

### ֧����ɨ�����

![֧����ɨ�����](https://image.xiaoxin.pro/2022/05/16/1f1a5f025c13c.png)

### ΢��ɨ�����

![΢��ɨ�����](https://image.xiaoxin.pro/2022/05/16/9c9906b102b29.png)
