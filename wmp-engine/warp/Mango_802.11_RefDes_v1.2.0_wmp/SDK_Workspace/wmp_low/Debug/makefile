################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include wmp_common/subdir.mk
-include wlan_mac_common/subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
ELFSIZE += \
wmp_low.elf.size \

ELFCHECK += \
wmp_low.elf.elfcheck \


# All Target
all: wmp_low.elf secondary-outputs

# Tool invocations
wmp_low.elf: $(OBJS) ../src/lscript.ld $(USER_OBJS)
	@echo Building target: $@
	@echo Invoking: MicroBlaze gcc linker
	mb-gcc -Wl,--no-relax -Wl,-T -Wl,../src/lscript.ld -L../../wlan_bsp_cpu_low/mb_low/lib -mlittle-endian -mxl-barrel-shift -mxl-pattern-compare -mcpu=v8.40.b -mno-xl-soft-mul -o"wmp_low.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo Finished building target: $@
	@echo ' '

wmp_low.elf.size: wmp_low.elf
	@echo Invoking: MicroBlaze Print Size
	mb-size wmp_low.elf  |tee "wmp_low.elf.size"
	@echo Finished building: $@
	@echo ' '

wmp_low.elf.elfcheck: wmp_low.elf
	@echo Invoking: Xilinx ELF Check
	elfcheck wmp_low.elf -hw ../../wlan_xps_v32_hw_platform/system.xml -pe mb_low  |tee "wmp_low.elf.elfcheck"
	@echo Finished building: $@
	@echo ' '

# Other Targets
clean:
	-$(RM) $(OBJS)$(C_DEPS)$(EXECUTABLES)$(ELFSIZE)$(ELFCHECK)$(S_UPPER_DEPS) wmp_low.elf
	-@echo ' '

secondary-outputs: $(ELFSIZE) $(ELFCHECK)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
