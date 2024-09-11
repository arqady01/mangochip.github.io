| 匹配方式 | 匹配内容 | 举例 |
|--|--|--|
DOMAIN | 匹配完整域名 | ad.com
DOMAIN-SUFFIX | 匹配域名后缀 | google.com
DOMAIN-KEYWORD | 使用域名关键字匹配 | google
DOMAIN-REGEX | 域名正则表达式匹配 | ^abc.*com
GEOSITE | 匹配 Geosite 内的域名 | youtube
IP-CIDR/IP-CIDR6 | 匹配 IP 地址范围IP-CIDR和IP-CIDR6效果是一样的，IP-CIDR6只是一个别名 | 127.0.0.0/82620:0:2d0:200::7/32
IP-SUFFIX | 匹配 IP 后缀范围 | 8.8.8.8/24
IP-ASN | 匹配 IP 所属 ASN | 13335
GEOIP | 匹配 IP 所属国家代码 | CN
SRC-GEOIP | 匹配来源 IP 所属国家代码 | cn
SRC-IP-ASN | 匹配来源 IP 所属 ASN | 9808
SRC-IP-CIDR | 匹配来源 IP 地址范围 | 192.168.1.201/32
SRC-IP-SUFFIX | 匹配来源 IP 后缀范围 | 192.168.1.201/8
DST-PORT | 匹配请求目标端口范围 | 80
SRC-PORT | 匹配请求来源端口范围 | 7777
IN-PORT | 匹配入站端口,可用端口范围 | 7890
IN-TYPE | 匹配入站类型 | SOCKS/HTTP
IN-USER | 匹配入站用户名，支持使用 / 分隔多个用户名 | linuxdo
IN-NAME | 匹配入站名称 | ss
PROCESS-PATH | 使用完整进程路径匹配 | D:\chrome.exe
PROCESS-PATH-REGEX | 使用进程路径正则表达式匹配 | *bin/wget
PROCESS-NAME | 使用进程匹配，在Android平台可以匹配包名 | chrome.exe
PROCESS-NAME-REGEX | 使用进程名称正则表达式匹配，在Android平台可以匹配包名 | curl$
UID | 匹配 Linux USER ID | 1001
NETWORK | 匹配tcp或者udp | udp
DSCP | 匹配DSCP标记 (仅限 tproxy udp 入站) | 4
RULE-SET | 引用规则集合，需配置rule-providers | providername
AND/OR/NOT | 逻辑规则，需要注意括号的使用 | ((DOMAIN,baidu.com),(NETWORK,UDP))
SUB-RULE | 匹配至子规则,需要注意括号的使用 | (NETWORK,tcp)
MATCH | 匹配所有请求，无需条件