# 在Ubuntu24上配置clash

## 下载安装

```bash
# 下载
wget https://git.opclash.com/kehuduan/clash/clash-linux-amd64-v1.18.0.gz

# 解压文件
gzip -d clash-linux-amd64-v1.18.0.gz

# 给予权限
chmod +x clash-linux-amd64-v1.18.0

# 改名移动
mv clash-linux-amd64-v1.18.0 /usr/local/bin/clash

# 查看版本
clash -v
```

## 配置

先运行一下然后`Ctrl + c`关闭，生成配置文件，在`~/.config/clash`中

如果运行后发现下载不了`Country.mmdb`或者半天都下载不完，这里就手动替换新的

可以在[这里]([clash/mmdb.md at main · chukangkang/clash · GitHub](https://github.com/chukangkang/clash/blob/main/mmdb.md))下载，或者用[我的](./src/Country.mmdb)

```bash
# 进入文件夹
cd ~/.config/clash

# 删除
rm -rf Country.mmdb

# 换成新的
cp [下载的Country.mmdb的路径] ./
```

## 使用

```bash
# 在clash配置文件目录下设置订阅链接
wget -O config.yaml [订阅地址]

# 启动
clash
```

然后设置系统代理就行了

```
HTTP: 127.0.0.1:7890
HTTPS: 127.0.0.1:7890
SOCK HOST: 127.0.0.1:7891
```
