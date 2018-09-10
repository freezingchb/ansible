# 环境操作相关

### 测试环境基础环境
| 机器 | 描述 |
| ---- | ---- |
| 192.168.1.119 | green.local，gitlab 等 |
| 192.168.1.181 | blue.local 等|

### 基础环境启动
#### 181 机器
#### 119 机器
```
// 检查系统时间
date
// 如果与当前日期时间不一致，则修订，否则后面启动会不成功
date -s 2018-09-03
date -s 15:49:49

// 启动docker
systemctl start docker

// 启动 gitlab-hl
docker start gitlab-hl

// 启动 gitlab-runner-hl
docker start gitlab-runner-hl

// 启动 外网ip指向内网机器
cd /opt/frp-....../
./frpc -c frpc.ini
```

### 按照脚本执行机器的playbook
```
// 示例 181
ansible-playbook 181.yml
```


