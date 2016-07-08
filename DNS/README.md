# DNS 

## 1.查询实际IP地址

```
nslookup www.gcssloop.com           // 查询实际IP(包括经过的重定向)

nslookup -debug www.gcssloop.com    // 查询实际IP(调试模式，包括查询过程信息)

dig  www.gcssloop.com               // 查询链
```
