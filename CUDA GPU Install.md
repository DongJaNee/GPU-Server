
## 1. GPU Driver 설치 

```
# 업데이트
sudo apt update 

# gcc설치 
sudo apt install build-essential 

# gcc 버전 확인 
gcc --version

# Nouveau 드라이버 비활성화 
echo -e "blacklist nouveau\noptions nouveau modeset=0" | sudo tee /etc/modprobe.d/blacklist-nouveau.conf

# initramfs 업데이트 
sudo update-initramfs -u

# 재부팅(업데이트 적용)
reboot

# Driver 설치  (ex 535버전)
sudo apt install nvidia-driver-535

# 재부팅 (driver가 바로 안올라왔을 경우) 
reboot 

# 드라이버 설치 확인 
nvidia-smi
```

![image](https://github.com/user-attachments/assets/a961edab-43f0-4e82-912f-c1a0f3e06df3)


## 2. Cuda 설치 
```
# 파일 다운 (ex 12.2 ToolKit)

wget https://developer.download.nvidia.com/compute/cuda/12.2.2/local_installers/cuda_12.2.2_535.104.05_linux.run

# 설치 
sudo sh cuda_12.2.2_535.104.05_linux.run
```

## 3. Cuda 시스템에 적용하기 
```
# vim 편집기 설치 
sudo apt install vim -y

# bashrc 편집
vi ~/.bashrc

# cuda 버전에 맞게 변경 (ex cuda 12.2)
export PATH=/usr/local/cuda-12.2/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda-12.2/lib64:$LD_LIBRARY_PATH

※ 내용 입력 :< i >
※ 나가기 : < :q! >
※ 저장하고 나가기 : < :wq >

# cuda 설치 확인
nvcc -V
```

## 4. GPU 작동 Test
```
# hashcat -b
```

![image](https://github.com/user-attachments/assets/66313262-b66a-4260-832f-ce5d5aae5dae)


## KTNF Server BMC 연결 방법

### IPMI 포트 연결
- **로컬 URL**: [https://192.168.1.199/](https://192.168.1.199/)
- **기본 ID**: admin
- **기본 암호**: qwe123123

## CUDA 버전 참고사항

CUDA 버전 선택 시 참고할 수 있는 공식 문서:
- [CUDA Toolkit Release Notes](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html)
- [CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive)
