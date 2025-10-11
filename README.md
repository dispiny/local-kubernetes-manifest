yum install -y cloud-utils-growpart.noarch
growpart /dev/sda 3
pvresize /dev/sda3
lvextend -l +100%FREE /dev/mapper/rl-root
xfs_growfs /dev/mapper/rl-root
df -H | grep mapper



kubeadm token create --print-join-command
