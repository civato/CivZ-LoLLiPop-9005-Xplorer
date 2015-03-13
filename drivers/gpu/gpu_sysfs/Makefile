# ==================================
# Start ----- Mali T6xx device -----
ifneq ($(CONFIG_MODULES),y)
$(error CONFIG_MODULES. This module won't work. Please enable CONFIG_MODULES in kernel config.)
endif

obj-m := gpu_sysfs.o

# Common files.
gpu_sysfs-y :=	gpu_sysfs_main.o \
		        gpu_sysfs_util.o


# Platform specific files.


# ==================================
# Start --------- Qualcomm ---------
ifeq ($(CONFIG_MSM_KGSL),y)

gpu_sysfs-y +=	gpu_sysfs_target_kgsl.o
# Verify: target specific file is defined.
GPU_SYSFS_TARGET_FILE_DEFINED=1

endif
# End ---------- Qualcomm ----------
# ==================================




clean:
	rm -f *.o .*.cmd modules.order Module.symvers gpu_sysfs.ko gpu_sysfs.mod.c
	rm -rf .tmp_versions
