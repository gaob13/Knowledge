找文段
```bash
$ grep -r pattern <dir>
```
加权限
```
gaobin  ALL=(ALL:ALL) NOPASSWD: ALL
```
改密码
```
echo user:pass | /usr/sbin/chpasswd
# 以下是以前的改法
echo password | passwd --stdin root
```
/tmp
```
/tmp的权限应该是777
```
