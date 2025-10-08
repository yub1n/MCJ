# git 初始化设置

配置用户，邮箱

```cmd
git config --global user.name "your name"

git config --global user.email "your email"
```

生成 ssh 密钥，不用登录

```cmd
ssh-keygen -t rsa -C "your email"
```

拷贝公钥，不包含换行符

克隆到本地

```cmd
git clone ssh@github.com
```