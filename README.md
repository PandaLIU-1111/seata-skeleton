# 快速上手 seata-php 开发


> 这篇文章主要是教大家如何更加容易上手,并且参与到 `seata/seata-php` 的开发中来，好了废话不多说，看下面的内容吧


在文章开始前，可以先回顾一下之前的 [开发指南](https://learnku.com/articles/70094)


由于考虑到开发指南的内容还是较为繁琐的的，所以给大家提供一系列的工具来减少大家搭建环境的麻烦

## php 环境搭建

`php` 环境搭建可以使用 [box](https://github.com/hyperf/box) 这个工具来快速的搭建环境

## 注意

如果你是 mac 用户需要给 box 工具进行授权


#### 下载 box 工具

##### Mac

```base
wget https://github.com/hyperf/box/releases/download/v0.0.3/box_php8.1_x86_64_macos -O box
sudo mv ./box /usr/local/bin/box
sudo chmod 755 /usr/local/bin/box
// Make sure /usr/local/bin/box in your $PATH env, or put `box` into any path in $PATH env that you want
```

##### Linux x86_64

```base
wget https://github.com/hyperf/box/releases/download/v0.0.3/box_php8.1_x86_64_linux -O box
sudo mv ./box /usr/local/bin/box
sudo chmod 755 /usr/local/bin/box
// Make sure /usr/local/bin/box in your $PATH env, or put `box` into any path in $PATH env that you want
```
##### Linux aarch64

```base
wget https://github.com/hyperf/box/releases/download/v0.0.3/box_php8.1_aarch64_linux -O box
sudo mv ./box /usr/local/bin/box
sudo chmod 755 /usr/local/bin/box
// Make sure /usr/local/bin/box in your $PATH env, or put `box` into any path in $PATH env that you want
```

---------------------------------------
- 使用 box 时，创建 github access token 权限需要`repo`、`workflow`
---------------------------------------

当 `box` 下载好后，我们接下来来下载 `php8.0` 版本

```
# 下载 php8.0
box get php@8.0
# 将 box 设置为 php8.0 版本
box config set-php-version 8.0
```

通过 `box` 下载 `composer`

注意：对应的 PHP 执行文件不一样，就会导致 PHP 版本和扩展情况不一样
```
# 下载 composer
box get composer
```

环境搭建完毕过后，找一个目录来存放我们开发的代码

```
# 找个地方创建一个目录
mkdir ./seata

# 进入到目录内
cd ./seata

# 下载 seata骨架包
git clone https://github.com/PandaLIU-1111/seata-skeleton

# 下载 seata/seata-php 组件包
git clone git@github.com:seata/seata-php.git

# 进入到 seata骨架包内
cd seata-skeleton

# 执行 composer 更新项目内的组件包
box composer update -o

# 查看是否与 seata/seata-php 建立软连接
ls -al vendor | grep seata

# 查看命令执行后是否有以下内容
 ...
 seata -> ../../../seata-php/  // 与 seata/seata-php 包建立软连接
 ...
 
 # 启动项目
 
 box php bin/hyperf.php start
```













