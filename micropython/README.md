# 擦除ESP8266闪存
esptool --port COM12 erase_flash

# 烧录固件
esptool --port COM12 --baud 115200 write_flash -fm qio -fs detect 0 D:\xxxxx\ESP8266_GENERIC-FLASH_1M-20240222-v1.22.2.bin