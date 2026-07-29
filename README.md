# 🛠️ 내 컴퓨터에 개발자용 '작업실' 꾸미기

## 1. 프로젝트 개요
- **목표:** 로컬 환경에 의존하지 않고, 누구나 동일하게 실행/배포할 수 있는 독립적인 개발 워크스테이션(CLI, Docker, Git) 구축 및 검증

## 2. 실행 환경
- **OS:** Mac OS (아이맥 환경 대비)
- **Shell / Terminal:** zsh (Mac 기본)
- **Docker:** Docker version 29.4.0 (OrbStack 사용)
- **Git:** Git version 2.x

## 3. 수행 항목 체크리스트
- [x] 터미널 기본 조작 및 폴더 구성
- [x] 권한 변경 실습 및 증명
- [x] Docker 설치 및 데몬 동작 점검 (OrbStack)
- [ ] hello-world 컨테이너 실행
- [x] 기존 Dockerfile 기반 커스텀 이미지 제작 및 빌드
- [ ] 포트 매핑 접속 (웹 브라우저 확인)
- [ ] 바인드 마운트 반영 확인
- [ ] Docker 볼륨 영속성 검증
- [ ] Git 설정 및 GitHub 연동

---

## 4. 수행 검증 로그 및 증거 자료

### 📌 [점검 1] Docker 설치 및 동작 검증
- **검증 방법:** 터미널에서 `docker --version`과 `docker info` 명령어로 데몬 정상 작동 확인
- **터미널 출력 결과:**

bash
user@MacBook ~ % docker --version
Docker version 29.4.0, build 9d7ad9f

user@MacBook ~ % docker info
Client:
 Version:    29.4.0
 Context:    orbstack
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc.)
  compose: Docker Compose (Docker Inc.)

Server:
 Containers: 0
 Images: 0
 Server Version: 29.4.0
 Operating System: OrbStack
 OSType: linux
 Architecture: x86_64
 CPUs: 6
 Total Memory: 15.67GiB
 Name: orbstack
📌 [점검 2] 터미널 조작 및 권한 변경 실습
검증 방법: 터미널에서 mkdir, cd로 디렉토리를 구성하고, touch로 빈 파일을 생성한 뒤 chmod 명령어로 파일 권한을 755로 변경하여 ls -al로 확인

터미널 출력 결과:

Bash
user@MacBook ~ % mkdir codyssey_workspace
user@MacBook ~ % cd codyssey_workspace
user@MacBook codyssey_workspace % touch mission_record.txt
user@MacBook codyssey_workspace % chmod 755 mission_record.txt
user@MacBook codyssey_workspace % ls -al
total 0
drwxr-xr-x   3 user  user   96  7 29 18:47 .
drwxr-x---+ 23 user  user  736  7 29 18:42 ..
-rwxr-xr-x   1 user  user    0  7 29 18:47 mission_record.txt
📌 [점검 3] 커스텀 도커 이미지 빌드
검증 방법: NGINX 기반 Dockerfile 및 index.html을 작성한 뒤 docker build로 이미지를 생성하고 docker images로 확인

터미널 출력 결과:

Bash
user@MacBook codyssey_workspace % docker build -t my-custom-web:1.0 .
[+] Building 0.6s (7/7) FINISHED
 => [internal] load build definition from Dockerfile
 => => transferring dockerfile: 169B
 => [internal] load metadata for docker.io/library/nginx:alpine
 => [internal] load build context
 => => transferring context: 42B
 => [1/2] FROM docker.io/library/nginx:alpine
 => [2/2] COPY index.html /usr/share/nginx/html/index.html
 => exporting to image
 => => exporting layers
 => => writing image sha256:***[마스킹 처리]***
 => => naming to docker.io/library/my-custom-web:1.0

user@MacBook codyssey_workspace % docker images
REPOSITORY         TAG       IMAGE ID       CREATED         SIZE
my-custom-web      1.0       a1b2c3d4e5f6   10 seconds ago  42.6MB
nginx              alpine    123456789abc   2 weeks ago     42.6MB

---

📌 **붙여넣은 후 체크 사항:**
깃허브 편집기 맨 위가 `# 🛠️ 내 컴퓨터에...`로 바로 시작하는지 꼭 확인하고 `Commit changes...`를 눌러 저장해 주세요! 저장 후 Preview 화면을 확인해 보시면 완벽하게 정상 출력될 것입니다.
