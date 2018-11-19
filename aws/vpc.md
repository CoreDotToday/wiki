<!-- TITLE: Vpc -->
<!-- SUBTITLE: A quick summary of Vpc -->

# VPC Setting
## Private Address Space
The Internet Assigned Numbers Authority (IANA) has reserved the
following three blocks of the IP address space for private internets:

- 10.0.0.0 - 10.255.255.255 (10/8 prefix)
- 172.16.0.0 - 172.31.255.255 (172.16/12 prefix)
- 192.168.0.0 - 192.168.255.255 (192.168/16 prefix)

## Route Table
- VPC내의 네트워크 트래픽을 전달

## Internet Gateway
- 외부망과 연결

## 외부 연결
Route Table에서 Routing 경로를 추가함.
새로 생성한 Internet Gateway를 0.0.0.0/0으로 통신하도록 설정.