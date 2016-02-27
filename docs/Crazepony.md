CJMCU原理图
Naze32原理图
Ubuntu下Cleanflight GUI的烧写
Ubuntu下ISP烧写

Linux下ISP烧写固件：
sudo ./stm32loader.py -e -w -v -p /dev/ttyUSB0 test.bin

把Hex文件转化为二进制文件：
arm-none-eabi-objcopy -I ihex -O binary cleanflight_CJMCU.hex test.bin

## LEDs

| 机臂LED | STM32 |
| ------  | ----- |
| M1      | PA11  |
| M2      | PA8   |
| M3      | PB1   |
| M4      | PB3   |


## Motor Connections

In standard QUADX configuration, the motors are mapped:

| Cleanflight | Crazepony  | STM32 |
| ----------- | ------ | ----- |
| Motor 1     | M2 | PA1 |
| Motor 2     | M3 | PA2 |
| Motor 3     | M1 | PA0 |
| Motor 4     | M4 | PA3 |

It is therefore simplest to wire the motors:
 * Motor 1 -> Clockwise
 * Motor 2 -> Anti-Clockwise
 * Motor 3 -> Clockwise
 * Motor 4 -> Anti-Clockwise
