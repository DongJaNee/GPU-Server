1. Ubuntu ISO File Download



2. rufus로 USB에 Mount 

3. Server에 Ubuntu Mount하고 실행 

4. Driver : RTX3090 --> Nvidia Driver 570.144 

기본 내장된오픈소스 NVIDIA 드라이버에  Nvidia Driver 570.144 버전이 없을 시 
```명령어
1. 기본 패키지 설치
sudo apt update (패키지 목록을 최신 상태로 업데이트)
sudo apt install build-essential dkms linux-headers-$(uname -r) -y (커널 모듈 빌드에 필요한 필수 패키지와 헤더 파일을 설치)

2. Nouveau 드라이버 비활성화 
echo -e "blacklist nouveau\noptions nouveau modeset=0" | sudo tee /etc/modprobe.d/blacklist-nouveau.conf (Nouveau 드라이버 비활성화)
sudo update-initramfs -u (변경 사항을 반영하여 initramfs 업데이트)
sudo reboot (시스템 재부팅 Nouveau 비활성화 적용)

3. NVIDIA 드라이버 설치
 
chmod +x NVIDIA-Linux-x86_64-570.144.run
sudo ./NVIDIA-Linux-x86_64-570.144.run

4. 섪치 확인
nvidia-smi
 
 
 
