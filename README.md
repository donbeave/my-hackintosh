# my-hackintosh

## CPU Model

```bash
cat /proc/cpuinfo | grep 'model name'
```

## GPU Model

```bash
lspci | grep -i --color 'vga\|3d\|2d'
```

## Chipset Model

```bash
dmidecode -t baseboard
```

## Keyboard, Trackpad and Touchscreen Connection Type

```bash
dmesg |grep -i 'input'
```

## Audio Codec

```bash
aplay -l
```

## Network Controller models

Basic info:

```bash
lspci | grep -i 'network'
```

More in-depth info:

```bash
lshw -class network
```

## Drive Model

```bash
lshw -class disk -class storage
```
