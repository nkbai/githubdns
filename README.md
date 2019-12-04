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
sudo githubdns
```
### 默认域名
默认修改以下域名
```
codeload.github.com
github.com
github.global.ssl.fastly.net
```
可以通过--domains参数来覆盖默认设置

## 工作原理
去ipaddress.com抓取你指定的域名对应的ip地址,然后写入到系统的hosts文件中
所以要正常运行必须以root权限运行.
