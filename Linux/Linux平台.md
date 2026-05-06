# Linux平台





## 常见操作

### 免密登录

```bash
# 生成秘钥对(若需要生成多个的时候, 只需要指定不同的邮箱,并且回车后指定文件名称,如:gitee_id_rsa)
ssh-keygen -t rsa -C "你的邮箱@xxx.com"

# 将公钥推送到远端(实现免密登录)
## Linux
ssh-copy-id -i .ssh/id_rsa.pub  用户名字@192.168.x.xxx
## Windows
cat .\id_rsa.pub | ssh root@122.51.15.110 "cat >> ~/.ssh/authorized_keys"

# 测试平台连通性
ssh -T git@gihub.com
```

