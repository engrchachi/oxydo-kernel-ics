ifneq ($(KERNELRELEASE),)
# kbuild part of makefile

obj-$(CONFIG_BTRFS_FS) := btrfs.o
btrfs-y := super.o ctree.o extent-tree.o print-tree.o root-tree.o dir-item.o \
	   file-item.o inode-item.o inode-map.o disk-io.o \
	   transaction.o inode.o file.o tree-defrag.o \
	   extent_map.o sysfs.o struct-funcs.o xattr.o ordered-data.o \
	   extent_io.o volumes.o async-thread.o ioctl.o locking.o orphan.o \
	   ref-cache.o export.o tree-log.o acl.o free-space-cache.o zlib.o \
	   compression.o
else

# Normal Makefile

KERNELDIR := /lib/modules/`uname -r`/build
all:
	$(MAKE) -C $(KERNELDIR) M=`pwd` CONFIG_BTRFS_FS=m modules

modules_install:
	$(MAKE) -C $(KERNELDIR) M=`pwd` modules_install
clean:
	$(MAKE) -C $(KERNELDIR) M=`pwd` clean

endif
