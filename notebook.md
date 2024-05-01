### look for devices
```shell
ioreg -p IOUSB
```

### look for devices (extended)
```shell
ioreg -w0 -l -p IOUSB
```

### look for devices (another way)
```shell
system_profiler SPUSBDataType
```

we are looking for a device
```text
Product ID: 0x8840 = 34880
 Vendor ID: 0x1189 = 4489 (Trisat Industrial Co., Ltd.)
```

### validate
```shell
ch57x-keyboard-tool validate < mapping-clockwise-1.yaml
```

### upload
```shell
sudo ch57x-keyboard-tool upload < mapping-clockwise-1.yaml
```
