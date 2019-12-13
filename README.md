# githubdns
一键加速国内github访问速度

## 安装
可以下载release中的各个编译好的二进制程序,也可以自行编译.
```bash
cargo build --release
```
## 使用
### windows
请修改程序权限,以管理员运行. 然后双击即可.
### unix
```bash
sudo ghdns
# 或者自定义一些空格分隔的域名
# sudo ghdns --domains "github.com codeload.github.com"
```
### 默认域名
默认修改以下域名
```
github.com
codeload.github.com
assets-cdn.github.com
github.global.ssl.fastly.net
stackoverflow.com
stackexchange.com
superuser.com
```
可以通过--domains参数来覆盖默认设置

## 工作原理
去ipaddress.com抓取你指定的域名对应的ip地址,然后写入到系统的hosts文件中
所以要正常运行必须以root权限运行.

## hosts所在文件夹
Windows 
位于 C:\Windows\System32\drivers\etc\

Linux/MacOS/iOS/Android等类Unix系统
/etc/

## 清除DNS缓存
Windows
开始 -> 运行 -> 输入cmd -> 在CMD窗口输入  ： ipconfig  /flushdns

Linux-Ubuntu/Debian/Mint
终端输入 ：  sudo /etc/init.d/dns-clean start

Linux-CentOS/Redhat
终端输入 ：  systemctl restart network

Linux-其他
终端输入 ：  
sudo /etc/init.d/nscd restart
sudo /etc/init.d/named restart
sudo /etc/init.d/dnsmasq restart

Mac OS X终端输入 ：  sudo killall -HUP mDNSResponder

其他：断网，再开网；
终极方法： 重启机器；
