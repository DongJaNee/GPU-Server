## 1. USB 장치 확인.
```
lslbk
```

## 2. USB 마운트 폴더 만들기.
```
sudo mkdir -p /mnt/usb
```

## 3. USB 마운트 
```
sudo mount /dev/sda1 /mnt/usb
```

## 4. 파일 복사 
```
cp /mnt/usb/NVIDIA-Linux-x86_64-570.144.run ~/
```

## 5. 마운트 해제 
```
sudo umount /mnt/usb
```

## ※ 우분투 드라이버 호환 버전 확인 
```
ubunut-drivers devices
```
