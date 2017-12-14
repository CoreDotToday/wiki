<!-- TITLE: Basic -->
<!-- SUBTITLE: A quick summary of Basic -->

# Compression
## bz2
- Burrows-Wheeler algorithm을 사용한 압축방법
### 압축해라
`bzip2 ./file.txt`

### 만약 파일이 있으면 강제로 덮어 씌워서 압축해라
`bzip2 -f ./file.txt`

### 압축 풀어라
`bzip2 -d ./file.bz`

### 작업 후에 파일을 유지해라
`bzip2 -k ./file.bz`


## tgz
- tar을 gzip으로 압축함
- c : compression
- x : decompression
- v : show the process
- f : specific filename
- z : gzip compression
- p : keep with the permission

### 압축해라
`tar czvzf file.tar.gz file.txt`

### 압축 풀어라
`tar -xvzf file.tgz`

## 다수 파일 압축 풀기
- `unzip '*.zip'`
- `for z in *.zip; do unzip $z; done`


# NVIDIA-Driver
## Ubuntu 16.04 LTS
`sudo add-apt-repository ppa:graphics-drivers/ppa`
`sudo apt update`

`lspci -vnn | grep VGA`

Check the latest driver version at https://www.geforce.com/drivers

`sudo apt install nvidia-{version}`
`nvidia-smi` # Installation Check

To find Tesla Drivers, look at http://www.nvidia.com/Download/index.aspx

```
i) sudo dpkg -i nvidia-diag-driver-local-repo-ubuntu1604-384.81_1.0-1_amd64.deb
ii) sudo apt-get update
iii) sudo apt-get install cuda-drivers
iv) sudo reboot
```


# Font Installation
## 우분투에 나눔글꼴 설치
`sudo apt-get install fonts-nanum fonts-nanum-coding fonts-nanum-extra`
`fc-cache -f -v`

## Python Matplotlib 한글 표현
```
from matplotlib import font_manager, rc
font_name = font_manager.FontProperties(fname="/usr/share/fonts/truetype/nanum/NanumGothic.ttf").get_name()
rc('font', family=font_name)
plt.rcParams['axes.unicode_minus'] = False
```

- ~/.cache/matplotlib 을 비우는 것을 추천함.

# Ubuntu
## 저장소 변경
`vi /etc/apt/sources.list`
`:%s/kr.archive.ubuntu.com/ftp.daumkakao.com/`