# docker Verdaccio 本地配置

* conf: 配置文件和默认 htpasswd

```bash
docker-compose up
```

## 权限

对应配置：

```yaml
auth:
  htpasswd:
    file: /verdaccio/conf/htpasswd
    max_users: -1 # 不允许注册用户，即只能通过 htpasswd 添加用户
packages:
  '@jonge/*':
      access: $authenticated
      publish: $authenticated
```

默认 `@jonge/*` 包只有登陆用户可以发布/安装，已经添加了一个默认用户（在于 [conf/htpasswd](./conf/htpasswd) 里）

用户名: jonge
密码: 123456

可以通过这里自己生成：http://www.htaccesstools.com/htpasswd-generator/



