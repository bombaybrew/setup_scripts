### Setup
```
> curl -sfL https://get.k3s.io | sh -

[INFO]  Finding release for channel stable
[INFO]  Using v1.18.4+k3s1 as release
[INFO]  Downloading hash https://github.com/rancher/k3s/releases/download/v1.18.4+k3s1/sha256sum-amd64.txt
[INFO]  Downloading binary https://github.com/rancher/k3s/releases/download/v1.18.4+k3s1/k3s
[INFO]  Verifying binary download
[INFO]  Installing k3s to /usr/local/bin/k3s
[INFO]  Creating /usr/local/bin/kubectl symlink to k3s
[INFO]  Creating /usr/local/bin/crictl symlink to k3s
[INFO]  Skipping /usr/local/bin/ctr symlink to k3s, command exists in PATH at /usr/bin/ctr
[INFO]  Creating killall script /usr/local/bin/k3s-killall.sh
[INFO]  Creating uninstall script /usr/local/bin/k3s-uninstall.sh
[INFO]  env: Creating environment file /etc/systemd/system/k3s.service.env
[INFO]  systemd: Creating service file /etc/systemd/system/k3s.service
[INFO]  systemd: Enabling k3s unit
Created symlink /etc/systemd/system/multi-user.target.wants/k3s.service → /etc/systemd/system/k3s.service.
[INFO]  systemd: Starting k3s


> sudo kubectl get nodes
NAME     STATUS   ROLES    AGE   VERSION
madmax   Ready    master   16m   v1.18.4+k3s1


> sudo kubectl cluster-info
Kubernetes master is running at https://127.0.0.1:6443
CoreDNS is running at https://127.0.0.1:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
Metrics-server is running at https://127.0.0.1:6443/api/v1/namespaces/kube-system/services/https:metrics-server:/proxy


> sudo kubectl get namespaces
NAME                   STATUS   AGE
default                Active   18m
kube-system            Active   18m
kube-public            Active   18m
kube-node-lease        Active   18m
kubernetes-dashboard   Active   12m


> sudo crictl ps


```

### Uninstall
```
> sudo /usr/local/bin/k3s-uninstall.sh 

+ id -u
+ [ 0 -eq 0 ]
+ /usr/local/bin/k3s-killall.sh
+ [ -s /etc/systemd/system/k3s.service ]
+ basename /etc/systemd/system/k3s.service
+ systemctl stop k3s.service
+ [ -x /etc/init.d/k3s* ]
+ killtree 6514 6568 6605 7404 7522 9767 9798
+ kill -9 6514 6703 6997 6568 6719 7069 6605 6760 6894 7404 7482 7987 7522 7568 7871 7916 9767 9826 10076 9798 9835 9928
+ do_unmount /run/k3s
+ umount /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/f685f5a2792adcbe71b933c039dd2567b94710fa1dbc442234850768db410c35/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/e227f9bdc1843de94296777d2a2ca316b60037f2d39aa92c9e1c8f25e6003230/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/b8b08924d33a143bda745db0abd72503757e7eaf0a737b19d899bacbab1173ff/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/afe1953c569d146575c5e11649a2b3c9bc899d543f649f27d5c25b0dee224c81/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/9cea33f3a9c2659740230c91bda4c01feebae5c53f235a9cff773fe0173a52f0/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/87e1e1936c40e5977fd49c8894e925cb2dffacd161b0342a8bc1dd787d215b15/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/6a2212f93db471d5ffc17b48c9c228af31e8f23b796e24e23566e968aaf15a0a/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/5601e6e3fe2d0bf8448fa7cc940612475feeb7dda32a752ab5b59302fdef6831/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/41f993902ceeb0820ce14981f0cc9d174feb49320174860c07e13231aafc5f08/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/4013189e6a4ba885e8a5bb5f5e6002294d58bc9dd1106561018e6eacab6cb0fc/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/2c094208d7a07250f9400d3534f3b9d58727ed58c8f57449d6a5d32d28c422d7/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/2bcfc234653f99fc2a45051f60b1c453da25a16fee9c1797ca649b027c1b17cf/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/1e8e4eada03c9ec8e5e324a8e882511f2d073fb07fa5e580efd3344c0f6e0eff/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/053be0eafa7d381eb2dbedd414e49d50aa94a068c9ac52128be5b5764cb178a1/rootfs /run/k3s/containerd/io.containerd.runtime.v2.task/k8s.io/0015261f06d61dda19485d584f5cff428a797077fda463e3e8a3e52a483d3be1/rootfs /run/k3s/containerd/io.containerd.grpc.v1.cri/sandboxes/f685f5a2792adcbe71b933c039dd2567b94710fa1dbc442234850768db410c35/shm /run/k3s/containerd/io.containerd.grpc.v1.cri/sandboxes/9cea33f3a9c2659740230c91bda4c01feebae5c53f235a9cff773fe0173a52f0/shm /run/k3s/containerd/io.containerd.grpc.v1.cri/sandboxes/5601e6e3fe2d0bf8448fa7cc940612475feeb7dda32a752ab5b59302fdef6831/shm /run/k3s/containerd/io.containerd.grpc.v1.cri/sandboxes/41f993902ceeb0820ce14981f0cc9d174feb49320174860c07e13231aafc5f08/shm /run/k3s/containerd/io.containerd.grpc.v1.cri/sandboxes/4013189e6a4ba885e8a5bb5f5e6002294d58bc9dd1106561018e6eacab6cb0fc/shm /run/k3s/containerd/io.containerd.grpc.v1.cri/sandboxes/1e8e4eada03c9ec8e5e324a8e882511f2d073fb07fa5e580efd3344c0f6e0eff/shm /run/k3s/containerd/io.containerd.grpc.v1.cri/sandboxes/053be0eafa7d381eb2dbedd414e49d50aa94a068c9ac52128be5b5764cb178a1/shm
+ do_unmount /var/lib/rancher/k3s
+ do_unmount /var/lib/kubelet/pods
+ umount /var/lib/kubelet/pods/aa7ca393-4545-4aed-8b92-10b5ea7f995e/volumes/kubernetes.io~secret/coredns-token-x8lpq /var/lib/kubelet/pods/a7e0a131-d827-444e-b891-8c91eea69d3f/volumes/kubernetes.io~secret/default-token-wbkhg /var/lib/kubelet/pods/9fe2a68c-64d1-4135-8e57-1a92e02625ba/volumes/kubernetes.io~secret/traefik-token-drvrf /var/lib/kubelet/pods/9fe2a68c-64d1-4135-8e57-1a92e02625ba/volumes/kubernetes.io~secret/ssl /var/lib/kubelet/pods/9e277fd1-402c-4fb9-ab4f-b6960187c880/volumes/kubernetes.io~secret/kubernetes-dashboard-token-vxdvf /var/lib/kubelet/pods/9876a9d7-db09-46b4-a734-dabb6c270259/volumes/kubernetes.io~secret/metrics-server-token-2m9fl /var/lib/kubelet/pods/5d402256-ca33-4a5a-9951-4d9c797389ec/volumes/kubernetes.io~secret/local-path-provisioner-service-account-token-9tglx /var/lib/kubelet/pods/3347ba9c-8536-46e2-ab6f-eb9f51d28c5c/volumes/kubernetes.io~secret/kubernetes-dashboard-token-vxdvf /var/lib/kubelet/pods/3347ba9c-8536-46e2-ab6f-eb9f51d28c5c/volumes/kubernetes.io~secret/kubernetes-dashboard-certs
+ do_unmount /run/netns/cni-
+ umount /run/netns/cni-f2c85bba-7b80-efc5-7860-d1386b27c7ff /run/netns/cni-dd2d55ed-da52-53ca-530d-60c9f6221686 /run/netns/cni-dc3fd6d5-5151-4592-225e-1ffb84dea2fb /run/netns/cni-ac00f9dd-ffc8-7d90-e448-f188010fb647 /run/netns/cni-a1b1bdd3-7ac2-7e01-3e2a-305e7a4114e9 /run/netns/cni-31a2e9e1-86d6-86d9-aba1-78e5cffb9a73 /run/netns/cni-0451e2bd-36aa-f380-794c-4499b3eccaea
+ grep master cni0
+ read ignore iface ignore
+ ip link show
+ iface=vethf6ffac44
+ [ -z vethf6ffac44 ]
+ ip link delete vethf6ffac44
+ read ignore iface ignore
+ iface=veth75b515e5
+ [ -z veth75b515e5 ]
+ ip link delete veth75b515e5
+ read ignore iface ignore
+ iface=veth4b1b89c7
+ [ -z veth4b1b89c7 ]
+ ip link delete veth4b1b89c7
+ read ignore iface ignore
+ iface=vethce5133f0
+ [ -z vethce5133f0 ]
+ ip link delete vethce5133f0
+ read ignore iface ignore
+ iface=veth6b26ddab
+ [ -z veth6b26ddab ]
+ ip link delete veth6b26ddab
+ read ignore iface ignore
+ iface=veth9798e0e5
+ [ -z veth9798e0e5 ]
+ ip link delete veth9798e0e5
+ read ignore iface ignore
+ iface=vethe72b3228
+ [ -z vethe72b3228 ]
+ ip link delete vethe72b3228
+ read ignore iface ignore
+ ip link delete cni0
+ ip link delete flannel.1
+ rm -rf /var/lib/cni/
+ grep -v KUBE-
+ grep -v CNI-
+ iptables-restore
+ iptables-save
+ which systemctl
/usr/bin/systemctl
+ systemctl disable k3s
Removed /etc/systemd/system/multi-user.target.wants/k3s.service.
+ systemctl reset-failed k3s
+ systemctl daemon-reload
+ which rc-update
+ rm -f /etc/systemd/system/k3s.service
+ rm -f /etc/systemd/system/k3s.service.env
+ trap remove_uninstall EXIT
+ [ -L /usr/local/bin/kubectl ]
+ rm -f /usr/local/bin/kubectl
+ [ -L /usr/local/bin/crictl ]
+ rm -f /usr/local/bin/crictl
+ [ -L /usr/local/bin/ctr ]
+ rm -rf /etc/rancher/k3s
+ rm -rf /var/lib/rancher/k3s
+ rm -rf /var/lib/kubelet
+ rm -f /usr/local/bin/k3s
+ rm -f /usr/local/bin/k3s-killall.sh
+ remove_uninstall
+ rm -f /usr/local/bin/k3s-uninstall.sh
```