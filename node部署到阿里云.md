## 升级CentOS
yum -y update

## 安装node 
wget http://nodejs.org/dist/v7.0.0/node-v7.0.0.tar.gz

### 解压
tar -xzvf node-v7.0.0.tar.gz

### 进入解压后的文件夹
cd node-v7.0.0

### 执行配置脚本来进行编译预处理
./configure

### 编译源代码
make

### 当编译完成后，需要使之在系统范围内可用, 编译后的二进制文件将被放置到系统路径，默认情况下，Node二进制文件应该放在/user/local/bin/node文件夹下
make install

### 安装 express 和 pm2，这两个模块都推荐 global 安装
npm -g install express pm2

### 建立超级链接, 不然 sudo node 时会报 "command not found"
sudo ln -s /usr/local/bin/node /usr/bin/node
sudo ln -s /usr/local/lib/node /usr/lib/node
sudo ln -s /usr/local/bin/npm /usr/bin/npm
sudo ln -s /usr/local/bin/node-waf /usr/bin/node-waf
sudo ln -s /usr/local/bin/pm2 /usr/bin/pm2

## 安装mongodb
软件安装位置：/usr/local/mongodb
数据存放位置：/var/mongodb/data
日志存放位置：/var/mongodb/logs

###首先下载安装包
cd /usr/local
wget http://fastdl.mongodb.org/linux/mongodb-linux-x86_64-2.4.9.tgz
