# Tools and options
PREFIX  = arm-none-eabi
CC      = $(PREFIX)-gcc
AR      = $(PREFIX)-ar

# The flags passed to the compiler
CFLAGS  = -mthumb \
        -mcpu=cortex-m3 \
        -std=c99 \
        -Wall \
        -O3 \
        -c

# Paths
INC_PATHS   = -IInclude \
        -I../CMSIS/Include \
        -I../Device/ST/STM32F1xx/Include
LIB_PATHS   =
SRC_PATH    = Source/
OUT_PATH    = gcc/

# Libs
LIBS    = -lc

# Definitions
DEFS    = -DUSE_FULL_LL_DRIVER=1 \
        -DUSE_FULL_ASSERT=1 \
        -DSTM32F103x6 \
        -DDEBUG

OBJS    = $(OUT_PATH)stm32f1xx_ll_adc.o \
        $(OUT_PATH)stm32f1xx_ll_crc.o \
        $(OUT_PATH)stm32f1xx_ll_dac.o \
        $(OUT_PATH)stm32f1xx_ll_dma.o \
        $(OUT_PATH)stm32f1xx_ll_exti.o \
        $(OUT_PATH)stm32f1xx_ll_gpio.o \
        $(OUT_PATH)stm32f1xx_ll_i2c.o \
        $(OUT_PATH)stm32f1xx_ll_irq.o \
        $(OUT_PATH)stm32f1xx_ll_pwr.o \
        $(OUT_PATH)stm32f1xx_ll_rcc.o \
        $(OUT_PATH)stm32f1xx_ll_rtc.o \
        $(OUT_PATH)stm32f1xx_ll_spi.o \
        $(OUT_PATH)stm32f1xx_ll_tim.o \
        $(OUT_PATH)stm32f1xx_ll_usart.o \
        $(OUT_PATH)stm32f1xx_ll_utils.o \
        $(OUT_PATH)system_stm32f1xx.o

LIB = $(OUT_PATH)libdriver.a

#The main all target
all: $(LIB)
.PHONY: all

# Implicit rules
$(OUT_PATH)%.o: $(SRC_PATH)%.c Makefile
	$(CC) $(CFLAGS) $(INC_PATHS) $(DEFS) $(<) -o $(@)

# The libdriver.a
$(OUT_PATH)%.a: $(OBJS)
	$(AR) -cr $(@) $(^)
