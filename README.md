## before starting
TODO

## generate config files
```
$ kubeinit gen --master 1.1.1.2 --master 1.1.1.3 --master 1.1.1.4 \
               --etcd  1.1.1.2 --etcd 1.1.1.3 --etcd 1.1.1.4 \
               --loadbalance 1.1.1.2 --apply
```
--apply 生成配置立即执行 kubeinit apply, 不加这个参数只生成一些配置文件，方便定制需求去修改配置，修改完再apply

## install etcd and masters
```
$ kubeinit apply -bie
```
开关：
* -b 只初始化环境，拷贝bin文件，配置文件，导入镜像等
* -i 执行kubeadm init命令
* -e 启动etcd

## featrures
- [x] 自动生成多etcd节点compose文件
- [x] 自动生成kubeadm配置
- [x] 自动生成haproxy配置
- [x] 自动检测cgroup driver, 自动生成 kubelet配置文件

- [ ] 自动初始化节点配置，拷贝bin文件，导入镜像
- [ ] 自动初始化其它master节点配置
- [ ] 自动启动etcd集群，master集群
- [ ] 自动启动loadbalance
