# Bypass_cdn
绕过CDN查找网站的真实IP地址


## 简介
### 项目结构
    img
### 说明
 - 魔改了lijiejie的subDomainsBrute用于子域名扫描
 - 根据HTTP响应包长度在扫出的地址范围内寻找真实IP
 - 
## 示例
```
PS C:\Users\SH\Desktop\Bypass_cdn> python3 .\scan.py https://www.ghxi.com/
[+] 目标不存在CDN
[+] 220.167.108.138
```
```
PS C:\Users\SH\Desktop\Bypass_cdn> python3 .\scan.py https://www.runoob.com/
[+] 目标存在CDN: 七牛云
[+] phpinfo测试...
[+] 奇特ping测试...
[+] DNS解析历史记录...
[+] 子域名扫描...
[+] All Done. 1 found, 27450 scanned in 120.5 seconds.
[+] 扫描C段: 47.246.16.0/24
[*] 47.246.16.252       8       0
[+] 扫描C段: 113.200.15.0/24
[+] 扫描C段: 113.16.206.0/24
[*] 113.16.206.254      8       0
[+] 扫描C段: 113.96.109.0/24
[*] 113.96.109.115      8       0
[+] 扫描C段: 118.31.45.0/24
[*] 118.31.45.64        719     0
[*] 118.31.45.36        3547    0
[*] 118.31.45.76        26358   26358
[*] 118.31.45.5         1517    0
    ......
    ......
    ......
[+] 扫描C段: 219.147.154.0/24
[+] 扫描C段: 124.239.162.0/24
[+] 扫描C段: 223.15.226.0/24
[*] 223.15.226.208      8       0
[+] 扫描C段: 118.123.2.0/24
[*] 118.123.2.232       8       0
[+] 扫描C段: 111.6.226.0/24
[*] 111.6.226.250       8       0
[+] 找到可能的IP地址
61.168.100.115
```
> 考虑到很多网站的真实IP所在主机为反向代理，会根据host头转发到后端的负载均衡服务器，上面输出中ip后面跟着的两个数字，就是有host和无host的响应包大小

