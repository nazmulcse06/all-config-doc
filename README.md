# all-config-doc
###Oracle Linux 8: Kernel-based Virtual Machine (KVM) Virtualization

https://blogs.oracle.com/linux/post/oracle-linux-8-kernel-based-virtual-machine-kvm-virtualization-made-easy-with-short-training-videos

Enabling KVM on Oracle Linux 8

Check List:
for intel system:  grep -e 'vmx' /proc/cpuinfo

for AMD system: grep -e 'svm' /proc/cpuinfo

check cpu type: grep -e 'vendor_id' /proc/cpuinfo

check kvm module: lsmod | grep kvm

Module install: sudo dnf module install virt

Module check: sudo dnf module info virt

sudo dnf install virt-install virt-viewer

virt-host-validate

sudo systemctl start libvirtd.service

sudo systemctl enable libvirtd.service

sudo systemctl status libvirtd.service
