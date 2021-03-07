# MongoDB 安装
```
sudo apt install mongodb
sudo systemctl enable mongodb
```
# 运行 MongoDB
```
mongod --dbpath /var/www/html/leanote/data/ --logpath /var/www/html/leanote/data/mongod.log --fork
```
`/var/www/html/leanote/data/`换成你想要的路径
# 初始化数据库
```
mongorestore -h localhost -d leanote --dir /var/www/html/leanote/mongodb_backup/leanote_install_data/
```
`/var/www/html/leanote/`是你的leanote根目录
# 修改数据库
```
db.users.update({"Username":"admin"},{$set:{"Username":"your_username"}})
```
`your_username`是你需要的名字
```
db.users.update({"Username":"your_username"},{$set:{"UsernameRaw":"your_username","Verified" : true,"Email" : "your_email"}})
```
`your_username`与上条保持一致, `your_email`改为你的邮箱
# 修改参数
修改`conf/app.conf`, `admin`名字要修改成`your_username`, `secert`也要一定的修改
# 安装Leanote
```
etsid sh /var/www/html/leanote/bin/run.sh
```
`/var/www/html/leanote/`是你的leanote根目录
