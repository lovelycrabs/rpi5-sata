# RPI5 EMC2301 FAN Configuration

1. get overlay dts
```shell
wget https://raw.githubusercontent.com/lovelycrabs/rpi5-sata/refs/heads/main/overlays/rpi5/i2c-fan-lm75-overlay.dts
```

2. install overlay

```shell

dtc -I dts -O dtb -o i2c-fan-lm75.dtbo i2c-fan-lm75-overlay.dts

sudo cp i2c-fan-lm75.dtbo /boot/firmware/overlays
```

然后在/boot/firmware/config.tx追加：


```shell
必须确保开启i2c dtparam=i2c_arm=on
dtoverlay=i2c-fan-lm75
```
必须确保开启i2c dtparam=i2c_arm=on
