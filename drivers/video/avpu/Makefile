SRC := $(shell pwd)

ifeq ($(O),)
	include $(KERNEL_SRC)/.config
else
	include $(O)/.config
endif

obj-$(CONFIG_AVPU_DRIVER)      += jz_avpu/

all:
	$(MAKE) -C $(KERNEL_SRC) M=$(SRC) O=$(O) modules

modules_install:
	$(MAKE) -C $(KERNEL_SRC) M=$(SRC) modules_install

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(SRC) clean
