# ���curl: (60) Peer's Certificate has expiredcurl����
## ����
���ҵ�һ̨����ChatGPT Acadmic�ķ������У�ִ�������ѯʱ����
```bash
[root@iZ62hd9jlz4Z certs]#
curl(60) - "Peer's Certificate has expired."
```

## �������
����һͨ�����淢����ϵͳ��ʱ�䲻�ԡ�
```bash
#��ѯʱ��
[root@iZ62hd9jlz4Z certs]# timedatectl status|grep 'Time zone'
       Time zone: Asia/Shanghai (CST, +0800)
#��ѯʱ�䣬����ʱ����1970��
[root@iZ62hd9jlz4Z certs]# date
Sun Oct 22 21:55:19 CST 1970

#ͬ��ʱ���������ʱ��
[root@iZ62hd9jlz4Z certs]# ntpdate -u pool.ntp.org
22 Oct 21:56:54 ntpdate[26724]: adjust time server 61.239.100.40 offset 0.000637 sec

#��ѯʱ��
[root@iZ62hd9jlz4Z certs]# date
Sun Oct 22 21:55:19 CST 2023

```

## ������

ͬ��ʱ���������ʱ�䣬�ͽ�������⡣