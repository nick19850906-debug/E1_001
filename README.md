# E1_001
코디세이 1주차 미션_001
# 🛠️ 내 컴퓨터에 개발자용 '작업실' 꾸미기

## 1. 프로젝트 개요
- **목표:** 로컬 환경에 의존하지 않고, 누구나 동일하게 실행/배포할 수 있는 독립적인 개발 워크스테이션(CLI, Docker, Git) 구축 및 검증

## 2. 실행 환경
- **OS:** Mac OS (아이맥 환경 대비)
- **Shell / Terminal:** zsh (Mac 기본)
- **Docker:** (여기에 아까 확인한 도커 버전을 적어주세요! 예: 26.x.x / OrbStack 사용)
- **Git:** (나중에 확인 후 작성)

## 3. 수행 항목 체크리스트
- [ ] 터미널 기본 조작 및 폴더 구성
- [ ] 권한 변경 실습 및 증명
- [x] Docker 설치 및 데몬 동작 점검 (OrbStack)
- [ ] hello-world 컨테이너 실행
- [ ] 기존 Dockerfile 기반 커스텀 이미지 제작 및 빌드
- [ ] 포트 매핑 접속 (웹 브라우저 확인)
- [ ] 바인드 마운트 반영 확인
- [ ] Docker 볼륨 영속성 검증
- [ ] Git 설정 및 GitHub 연동

## 4. 수행 검증 로그 및 증거 자료

### 📌 [점검 1] Docker 설치 및 동작 검증
- **검증 방법:** 터미널에서 `docker --version`과 `docker info` 명령어로 데몬 정상 작동 확인
- **터미널 출력 결과:**
```bash
Last login: Wed Jul 29 17:42:08 on ttys002
************@c3r4s5 ~ % docker --version
Docker version 29.4.0, build 9d7ad9f
************@c3r4s5 ~ % docker info
Client:
 Version:    29.4.0
 Context:    orbstack
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.33.0
    Path:     /Users/************/.docker/cli-plugins/docker-buildx
  compose: Docker Compose (Docker Inc.)
    Version:  v5.1.2
    Path:     /Users/************/.docker/cli-plugins/docker-compose

Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 0
 Server Version: 29.4.0
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 77c84241c7cbdd9b4eca2591793e3d4f4317c590
 runc version: c241c0bb5e60a8e8c1b2e53d4eca8d0068d8d57e
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.19.13-orbstack-gbd1dc07b8cf4
 Operating System: OrbStack
 OSType: linux
 Architecture: x86_64
 CPUs: 6
 Total Memory: 15.67GiB
 Name: orbstack
 ID: b0d92ba2-4649-4df2-8f75-c91a1a35731d
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 Experimental: false
 Insecure Registries:
  ::1/128
  127.0.0.0/8
 Live Restore Enabled: false
 Product License: Community Engine
 Default Address Pools:
   Base: 192.168.97.0/24, Size: 24
   Base: 192.168.107.0/24, Size: 24
   Base: 192.168.117.0/24, Size: 24
   Base: 192.168.147.0/24, Size: 24
   Base: 192.168.148.0/24, Size: 24
   Base: 192.168.155.0/24, Size: 24
   Base: 192.168.156.0/24, Size: 24
   Base: 192.168.158.0/24, Size: 24
   Base: 192.168.163.0/24, Size: 24
   Base: 192.168.164.0/24, Size: 24
   Base: 192.168.165.0/24, Size: 24
   Base: 192.168.166.0/24, Size: 24
   Base: 192.168.167.0/24, Size: 24
   Base: 192.168.171.0/24, Size: 24
   Base: 192.168.172.0/24, Size: 24
   Base: 192.168.181.0/24, Size: 24
   Base: 192.168.183.0/24, Size: 24
   Base: 192.168.186.0/24, Size: 24
   Base: 192.168.207.0/24, Size: 24
   Base: 192.168.214.0/24, Size: 24
   Base: 192.168.215.0/24, Size: 24
   Base: 192.168.216.0/24, Size: 24
   Base: 192.168.223.0/24, Size: 24
   Base: 192.168.227.0/24, Size: 24
   Base: 192.168.228.0/24, Size: 24
   Base: 192.168.229.0/24, Size: 24
   Base: 192.168.237.0/24, Size: 24
   Base: 192.168.239.0/24, Size: 24
   Base: 192.168.242.0/24, Size: 24
   Base: 192.168.247.0/24, Size: 24
   Base: fd07:b51a:cc66:d000::/56, Size: 64
 Firewall Backend: iptables

WARNING: DOCKER_INSECURE_NO_IPTABLES_RAW is set
c1134czi5625@c3r4s5 ~ % 
