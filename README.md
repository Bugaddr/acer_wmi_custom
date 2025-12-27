# Summary of Modes

The acer-wmi driver for your Nitro AN515-58 supports three specific modes for pwm1_enable:

1. 2 = Auto (Default. Safe, quiet, capped around 4000 RPM).
2. 0 = Turbo (Max power. The ~7000 RPM mode you are looking for).
3. 1 = Custom (Allows you to set specific speeds using pwm1).

```bash
echo 2 | sudo tee /sys/class/hwmon/hwmon*/pwm*_enable
echo 127 | sudo tee /sys/class/hwmon/hwmon*/pwm{1,2}
```

## Building and loading the driver

```bash
make clean; make; sudo modprobe -r acer-wmi; sudo modprobe sparse-keymap; sudo insmod acer-wmi.ko
```
