Title: AWS Cognito
# 인증의 종류
## 서버 기반 인증
- 세션을 유지하기 위해 서버에서 유저들의 정보를 메모리 / 디스크 / 데이터베이스에 담음.
### Limitation
- 세션의 수 한계
- 확장이 복잡. 특히 CORS 처리 까다로움

## 토큰 기반 인증
- stateless (상태를 유지하지 않음)
- 


# AuthN vs AuthR
## 인증 Authentication (AuthN)
- 너 누구냐

## 인가 Authorization (AuthR)
- 무얼 허용하고 무얼 거부할 것인가

# Federation
![2018 06 05 204658](/uploads/cognito/2018-06-05-204658.png "2018 06 05 204658")

# Cognito Identity
## User Pools
- 유저 관리 (모바일, 웹에 로그인, 로그아웃 기능 쉽게 추가)
- 유저 디렉토리 생성 (완전 관리형)
- 이메일 인증, MFA 인증 등 안전 강화

### 기능
- Sign up, Sign in
- 이메일 혹은 전화번호 확인
- 패스워드 분실/리셋
- 사용자 프로파일
- SMS 기반 MFA
- 토큰 기반 인증 (OpenID Connect(OIDC), OAuth 2.0 지원)
- 안전한 원격 패스워드 프로토콜 (Sign in 시에 Secure Remote Password(SRP) 사용)
- SMS 기반 Multi factor 인증 (모바일 텍스트 메시징으로 보안 레이어 더 추가 가능)

![2018 06 05 205351](/uploads/cognito/2018-06-05-205351.png "2018 06 05 205351")

- User Pools 생성 및 관리 (리젼 별로 복수 개의 유저 풀을 생성, 설정, 삭제)
- 커스텀 속성 정의 (사용자 프로필에 사용할 커스텀 속성 정의)
- 속성에 대한 필수사항 설정
- 패스워드 정책 설정
- 유저 검색 (콘솔 혹은 API를 통해 이메일, 전화번호, 유저 이름 등 검색)
- 유저 관리 (유저 패스워드 리셋, 활성화, 유저 컨펌, MFA 사용, 유저 삭제, 글로벌 사인아웃 등)
## Federation Identities
3rd 파티 ID 제공자를 통해 로그인
AWS 리소스에 대한 앱의 접근에 대해 제어함



