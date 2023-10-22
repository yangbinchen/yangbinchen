# 解决curl: (60) Peer's Certificate has expiredcurl问题
## 现象
在我的一台运行ChatGPT Acadmic的服务器中，执行问题查询时报错：
```bash
[root@iZ62hd9jlz4Z certs]#
curl(60) - "Peer's Certificate has expired."
```

## 问题分析
查了一通，后面发现是系统的时间不对。
```bash
#查询时区
[root@iZ62hd9jlz4Z certs]# timedatectl status|grep 'Time zone'
       Time zone: Asia/Shanghai (CST, +0800)
#查询时间，发现时间是1970年
[root@iZ62hd9jlz4Z certs]# date
Sun Oct 22 21:55:19 CST 1970

#同步时间服务器的时间
[root@iZ62hd9jlz4Z certs]# ntpdate -u pool.ntp.org
22 Oct 21:56:54 ntpdate[26724]: adjust time server 61.239.100.40 offset 0.000637 sec

#查询时间
[root@iZ62hd9jlz4Z certs]# date
Sun Oct 22 21:55:19 CST 2023

```

## 问题解决

同步时间服务器的时间，就解决了问题。