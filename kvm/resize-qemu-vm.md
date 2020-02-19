### Power off the vim

* `virsh shutdown my-vm-01`
* `virsh destroy my-vm-01`

### Resize the image file

* `qemu-img resize my-vm-01.img +80GB`

### Start the server

* `virsh start my-vm-01`

### Log into the server

* `ssh user@hostname`

### Repartition the drive

Use parted or gparted.

This is incomplete, but a start.
