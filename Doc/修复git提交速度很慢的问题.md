## 修复git提交速度很慢的问题   

解决方法：
sudo vi /etc/hosts, 加入github的host地址
192.30.253.113 github.com
151.101.185.194 github.global.ssl.fastly.net

# 直接访问github可能不会立即生效，因为有DNS缓存，并没有按照最新的修改配置访问
刷新 DNS 缓存：
sudo /etc/init.d/dns-clean

# ip地址得到方式：
ping github.com 得到ip：192.30.253.113
ping github.global.ssl.fastly.net 得到ip：151.101.185.194

# 提交说明信息的时候, linux默认是nano编辑器
修改系统的配置默认为vim:
git config --global core.editor vim

# git提交每次都要输入账户密码问题：
解决方法：git config --global credential.helper store
