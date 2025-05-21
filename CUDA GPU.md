# CUDA GPU 가이드

## CUDA ToolKit 설치

NVIDIA CUDA Toolkit 12.2.2 다운로드 링크:
- [CUDA 12.2.2 Download Archive](https://developer.nvidia.com/cuda-12-2-2-download-archive?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local)

## KTNF Server BMC 연결 방법

### IPMI 포트 연결
- **로컬 URL**: [https://192.168.1.199/](https://192.168.1.199/)
- **기본 ID**: admin
- **기본 암호**: qwe123123

## 설치 가이드

### Ubuntu 22.04에 CUDA 12.2.2 설치하기

```bash
# 필수 패키지 설치
sudo apt update
sudo apt install build-essential

# CUDA 저장소 키 추가
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.0-1_all.deb
sudo dpkg -i cuda-keyring_1.0-1_all.deb

# CUDA 저장소 추가 및 설치
sudo apt-get update
sudo apt-get -y install cuda-12-2

# 환경 변수 설정
echo 'export PATH=/usr/local/cuda-12.2/bin:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda-12.2/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc

# 설치 확인
nvcc --version
```

### NVIDIA 드라이버 상태 확인

```bash
nvidia-smi
```

## BMC 사용 가이드

BMC(Baseboard Management Controller)는 서버의 원격 관리를 위한 인터페이스입니다.

### 주요 기능
- 전원 관리 (원격 켜기/끄기/재시작)
- 하드웨어 모니터링
- 원격 콘솔 접속
- 시스템 이벤트 로그 확인

### 접속 방법
1. 웹 브라우저에서 [https://192.168.1.199/](https://192.168.1.199/) 접속
2. 보안 경고가 표시될 경우 "고급" 선택 후 "안전하지 않음" 옵션으로 진행
3. 로그인 화면에서 다음 정보 입력:
   - 사용자 이름: admin
   - 비밀번호: qwe123123
