## ansible install redis
本脚本支持在CentOS7/8、RedHat7/8、Rocky Linux 8、Alma Linux 8
1.在ansible服务器侧添加准备安装vuls服务器的hosts

$ cat /etc/ansible/hosts 
```
[redis_centos8]
172.26.37.142 ansible_ssh_user=root ansible_ssh_pass='123456'

[redis_centos7]
172.26.37.201 ansible_ssh_user=root ansible_ssh_pass='123456'
```
2.下载ansible安装的playbook等文件

$ git clone git@github.com:arrow003/ansible_redis.git

$ cd ansible_redis

3.执行playbook（执行之前可以通过[vars]修改准备部署的目录

$ ansible-playbook ansible_redis_centos7.yaml

$ ansible-playbook ansible_redis_centos8.yaml

## 测试redis服务状态

$ redis-cli -h 172.26.37.201 -p 6379
```
172.26.37.201:6379> set 123 "test"
OK
172.26.37.201:6379> get 123
"test"
172.26.37.201:6379> 
```
