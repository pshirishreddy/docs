```Installing minikube on arch linux with KVM

1. Install kubectl https://kubernetes.io/docs/tasks/kubectl/install/
2. Install KVM Driver (https://github.com/kubernetes/minikube/blob/master/DRIVERS.md#kvm-driver)
   a. Install libvirt and qemu `pacman -S libvirt qemu-kvm`
   b. Add current user to libvirt group `sudo usermod -a -G libvirt $(whoami)`
   c. Update current session group `newgrp libvirt`
3. Start libvirt `systemctl start libvirtd.service`
4. Start default network using `virt-manager` or 
   a. `sudo virsh net-autostart default`
   b. `sudo virsh net-start default `
5. Start minikube with kvm `minikube --vm-driver=kvm start`
  
