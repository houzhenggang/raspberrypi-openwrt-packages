# openwrt packages for Raspberry-pi
## 소개
안녕하세요 엔텔스 오준호라고 합니다.
이 Git에 배포하는 openwrt packages는 라즈베리파이용으로 제작되었으며
라우터를 위한 오픈 소스인 openwrt를 jvm등 기존의 glibc 환경에서 사용 가능하도록 재컴파일을 하여 배포하는 제품입니다.



## 사용 환경
* Raspberry-pi (brcm2708)
* linux-x86_64
* eglibc-2.15
* gcc-4.8-linaro

## 사용방법 

1. git clone https://github.com/nTels-ohjunho/raspberrypi-openwrt-packages 를 수행하여 패키지를 로컬서버로 가져옵니다.
2. 받은 패키지 폴더를 FTP로 노출합니다.
3.  opkg.conf 에 FTP 주소로 경로를 변경합니다.

라즈베리파이 설치 후 /etc/opkg.conf를 변경하여 사용합니다. 
```
vi /etc/opkg.conf 
```
```
dest root /
dest ram /tmp
lists_dir ext /var/opkg-lists
option overlay_root /overlay
src/gz chaos_calmer_base [FTP주소]/base
src/gz chaos_calmer_luci [FTP주소]/luci
src/gz chaos_calmer_management [FTP주소]/management
src/gz chaos_calmer_oldpackages [FTP주소]/oldpackages
src/gz chaos_calmer_packages [FTP주소]/packages
src/gz chaos_calmer_routing [FTP주소]/routing
src/gz chaos_calmer_telephony[FTP주소]/telephony
```
```
opkg update
```
## Raspberry-pi 외의 다른 하드웨어 지원
엔텔스에서는 이외에도 openwrt에서 지원하는 모든 하드웨어를 지원합니다. 다른 디바이스 지원에 대해서는 연락주시기 바랍니다.

* 이메일: o9764@ntels.com
* 담당자: 오준호

## 재배포자
엔텔스 porduct개발팀 

* 이상훈
* 오준호
* 김유성

## License

See [LICENSE](LICENSE) file.
 
## Package Guidelines

See [CONTRIBUTING.md](CONTRIBUTING.md) file.


