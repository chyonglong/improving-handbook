

用户名和邮箱地址是本地git客户端的一个变量，不随git库而改变。

每次commit都会用用户名和邮箱纪录。

1、查看用户名和地址
```
git config user.name
git config user.email
```
2、修改用户名和地址
```
git config --global user.name "your name"
git config --global user.email "your email"
```

[参考资料](https://www.jianshu.com/p/d24e791a7679)

