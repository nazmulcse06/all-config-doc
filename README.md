# all-config-doc
###Oracle Linux 8: Kernel-based Virtual Machine (KVM) Virtualization

https://blogs.oracle.com/linux/post/oracle-linux-8-kernel-based-virtual-machine-kvm-virtualization-made-easy-with-short-training-videos

FreeBSD:
https://www.cyberciti.biz/faq/kvmvirtualization-virt-install-openbsd-unix-guest/?__cf_chl_captcha_tk__=pmd_B14XhRGhh8nAjdDeX8Zfd5N4JxpJKuIkWXVIchkGGcM-1629733931-0-gqNtZGzNAzujcnBszQl9

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



Bridge Network:

sudo nmcli conn show --active
sudo nmcli conn add type bridge con-name br0 ifname br0

static IP:

sudo nmcli conn modify br0 ipv4.address '192.168.1.1/24'

sudo nmcli conn modify br0 ipv4.gateway '192.168.1.1'

sudo nmcli conn modify br0 ipv4.dns '192.168.1.1'

sudo nmcli conn modify br0 ipv4.method manual

sudo nmcli conn add type ethernet slave-type bridge con-name bridge-br0 ifname ens5 master br0

sudo nmcli conn up br0

sudo nmcli conn down ens5

sudo nmcli conn show --active

sudo bridge link show


#!/bin/bash 
pg_dump -d postgres://postgres:postgres@192.168.122.21:5432/amigos -Fc > /tmp/dump55.dump
pg_restore -d postgres://postgres:postgres@192.168.122.22:5432/siemtest < /tmp/dump55.dump




ALTER SCHEMA siem RENAME TO siem2;
ALTER TABLE person
ADD COLUMN city VARCHAR;



