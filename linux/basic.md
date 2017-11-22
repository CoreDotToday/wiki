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


# Font Installation
## 우분투에 나눔글꼴 설치
`sudo apt-get install fonts-nanum fonts-nanum-coding fonts-nanum-extra`
`fc-cache -f -v`

## Python Matplotlib 한글 표현
```
from matplotlib import font_manager, rc
font_name = font_manager.FontProperties(fname="/usr/share/fonts/truetype/nanum/NanumGothic.ttf").get_name()
rc('font', family=font_name)
```