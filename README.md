# qemu-test

##建一顆虛擬硬碟
qemu-img create -f qcow2 ubuntu_vm.qcow2 40G

-f qcow2：使用 qcow2 格式（支援快照、可動態長大）
40G：虛擬磁碟大小（上限）


##mac env run ubuntu

qemu-system-x86_64 \                                               
  -accel tcg,thread=multi \
  -m 4096 \
  -cpu qemu64 \
  -smp 4 \
  -drive file=ubuntu_vm.qcow2,if=virtio,format=qcow2 \
  -cdrom ubuntu-24.04.3-desktop-amd64.iso \    
  -boot d \
  -nic user,model=virtio-net-pci



##安裝完從硬碟開機

qemu-system-x86_64 \
  -accel tcg,thread=multi \
  -m 4096 \
  -cpu qemu64 \
  -smp 4 \
  -drive file=ubuntu_vm.qcow2,if=virtio,format=qcow2 \
  -boot c \
  -nic user,model=virtio-net-pci


