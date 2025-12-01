# qemu-test

1.mac env run ubuntu
qemu-system-x86_64 \
  -accel tcg,thread=multi \
  -m 4096 \
  -cpu qemu64 \
  -smp 4 \
  -drive file=ubuntu_vm.qcow2,if=virtio,format=qcow2 \
  -cdrom ubuntu-24.04.3-live-server-amd64.iso \
  -boot d \
  -nic user,model=virtio-net-pci


2.安裝完從硬碟開機
qemu-system-x86_64 \
  -accel tcg,thread=multi \
  -m 4096 \
  -cpu qemu64 \
  -smp 4 \
  -drive file=ubuntu_vm.qcow2,if=virtio,format=qcow2 \
  -boot c \
  -nic user,model=virtio-net-pci


