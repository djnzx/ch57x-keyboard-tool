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
Device@14320000
id 0x1000034dd
Product ID: 0x8840 = 34880
 Vendor ID: 0x1189 = 4489 (Trisat Industrial Co., Ltd.)
```

### explore dependencies
```shell
cargo install cargo-tree --force
cargo-tree tree
```

### build & install
```shell
cargo install ch57x-keyboard-tool
```

### validate
```shell
ch57x-keyboard-tool validate < mapping-clockwise-1.yaml
ch57x-keyboard-tool validate < mapping-clockwise-test.yaml
```

### upload
```shell
sudo ch57x-keyboard-tool upload < mapping-clockwise-1.yaml
sudo ch57x-keyboard-tool upload < mapping-clockwise-test.yaml
sudo ch57x-keyboard-tool --vendor-id 4489 --product-id 34880 upload < mapping-clockwise-1.yaml
sudo ch57x-keyboard-tool --vendor-id 4489 --product-id 34880 upload < mapping-clockwise-test.yaml
```

### debug
```shell
sudo RUST_LOG=ch57x_keyboard_tool=debug target/debug/ch57x-keyboard-tool --vendor-id 4489 --product-id 34880 upload < mapping-clockwise-test.yaml
```