# docker-aws
### 스프링 부트 프로젝트를 도커로 빌드해서 aws에서 실행하는 과정
1. 스프링 이니셜라이저로 스프링 부트 프로젝트를 생성하여 깃허브에 업로드
2. aws ec2에 인스턴스를 생성하여 shell로 실행 후 깃 클론하여 프로젝트 다운로드
3. 해당 프로젝트에 도커파일을 빌드하여 도커 실행과 함께 프로젝트도 실행

### 세부사항
- 이니셜라이저로 빌드시 java17, gradle, jar로 설정
- 보다 편리하게 깃헙 이용을 위해 인텔리제이나 비주얼 코드를 사용
- aws 인스턴스 생성시 ubuntu(linux)의 프리티어 서버로 생성
- aws 인스턴스 접속을 위해 mobaxterm 프로그램을 사용
- shell에서 sudo su - (루트 권한으로 실행, 도커 사용을 위해 루트 권한 필요)
- 자바 실행을 위해 jdk 설치 (openjdk-17-jdk)
- sh gradlew, sh gradlew build (스프링 프로젝트를 실행하기 위한 환경설정)
- docker build -t docker-aws . (도커 파일 빌드)
- docker run -p 8090:8090 docker-aws (도커 컨테이너 실행)
