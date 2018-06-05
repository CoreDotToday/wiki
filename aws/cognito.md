Title: AWS Cognito
# AuthN vs AuthR
## 인증 Authentication (AuthN)
- 너 누구냐

## 인가 Authorization (AuthR)
- 무얼 허용하고 무얼 거부할 것인가


# 인증의 종류
## 서버 기반 인증
- 세션을 유지하기 위해 서버에서 유저들의 정보를 메모리 / 디스크 / 데이터베이스에 담음.
- 
### Limitation
- 세션의 수 한계
- 확장이 복잡. 특히 CORS 처리 까다로움

## 토큰 기반 인증
- stateless (상태를 유지하지 않음)
- scalability (토큰을 클라이언트에 저장하기 때문에)
- extensibility (로그인 정보의 확장성)

### 인증 절차
1. Sign in
2. 서버에서 해당 계정정보를 검증
3. 확인된 계정은 클라이언트에 정상 발급된 토큰을 증명하는 signature가 포함된 signed token을 발급
4. 클라이언트는 이후 서버에 요청할 때마다 전달받은 토큰을 HTTP 헤더 등에 포함하여 서버에 전달
5. 서버는 건너오는 토큰을 검증하고, 맞는 요청을 응답

# JWT
JSON Web Token
- JSON은 \n 등 개행문자 때문에 HTTP Header 등에 넣기 불편함. 보통 base64 인코딩을 통해 하나의 문자열로 변환하여 사용.
- Integrity를 위해 HMAC 방식을 사용함.
## SHA1-256 HMAC
1. 원본 메시지에서 해쉬값을 추출.
2. Secret key로 복호화시켜서 token 뒤에 붙임.


# Federation
![2018 06 05 204658](/uploads/cognito/2018-06-05-204658.png "2018 06 05 204658")

# Cognito Identity
## User Pools
Amazon Cognito User Pools 토큰은 RS256 알고리즘을 사용하여 서명됨.
https://aws.amazon.com/ko/blogs/korea/amazon-cognito-your-user-pools-now-generally-available/

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



# Reference

http://behonestar.tistory.com/112?category=694311

https://github.com/aws-samples/aws-serverless-workshops/tree/master/WebApplication

https://codeburst.io/tutorial-for-building-a-web-application-with-amazon-s3-lambda-dynamodb-and-api-gateway-6d3ddf77f15a

https://sanderknape.com/2017/02/getting-started-with-aws-cognito/
https://medium.freecodecamp.org/user-management-with-aws-cognito-3-3-last-steps-to-full-fledged-73f4a3a9f05e

예전 버전 : http://edtheron.me/projects/store-messages-aws-dynamodb-lambda-api-gateway-cognito
https://github.com/aws-samples/aws-amplify-graphql

서명 : https://docs.aws.amazon.com/ko_kr/general/latest/gr/sigv4-signed-request-examples.html
https://forums.aws.amazon.com/thread.jspa?threadID=246580
https://gist.github.com/dkarchmer/76499c17ff947e1f149c

https://www.slideshare.net/awskr/aws-77390313
https://www.slideshare.net/awskr/amazon-cognito-77390377
https://github.com/bskim/gamingonaws2017_serverless

https://serverless-stack.com/chapters/login-with-aws-cognito.html
https://github.com/AnomalyInnovations/serverless-stack-com/issues/38

https://github.com/awslabs/aws-serverless-auth-reference-app