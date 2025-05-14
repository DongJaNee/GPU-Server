## 0. 드라이버 필수 패키지 다운로드
```
sudo apt update
sudo apt install build-essential dkms linux-headers-$(uname -r)
```

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

## 6. 권한 부여 
```
cmhod +x ~/NVIDIA-Linux-x86_64-570.144.run
```

## 7. 실행
```
sudo ./NVIDIA-Linux-x86_64-570.144.run
```

## 8. reboot
```
sudo reboot
```

## 9. 설치확인
```
nvidia-smi
```

## ※ 우분투 드라이버 호환 버전 확인 
```
ubunut-drivers devices
```
