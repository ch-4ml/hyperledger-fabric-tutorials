# hyperledger-fabric-tutorials
hyperledger-fabric 실습입니다. fabric-samples의 basic network로 시작해서 organization 확장을 목표로 합니다.

<br>

## 개발 환경
ubuntu-18.04.3-live-server-amd64

<br>

## Docker 설치
이 튜토리얼에서는 Docker를 사용하여 리눅스 컨테이너 방식으로 다양한 가상 환경을 한 OS위에서 동작시키는 방식으로 hyperledger fabric network를 구축합니다. 따라서 Docker를 먼저 설치해줍니다.
```
// docker 설치
sudo apt install docker.io
sudo apt install docker-compose
sudo apt install software-properties-common

// 사용자에게 Docker 접근 권한 주기
sudo usermod -aG docker $USER

// 변경 사항 적용을 위해 재부팅
reboot
```

<br>

## curl, Node.js, Go 설치

- curl<br>
  command line에서 url을 이용한 http 요청을 보낼 수 있는 기능을 가진 패키지.<br>
  이 튜토리얼에서는 url 주소로 파일을 다운로드 하기 위해 사용.<br>

- Node.js<br>
  fabric-network 등 application에서 blockchain network에 접근할 수 있는 기능을 가진 모듈을 이용하기 위함.<br>
  
- Go<br>
  chaincode 개발에 사용할 언어.<br>
  
```
// curl 설치
sudo apt-get install curl

// 패키지 매니저 업데이트
sudo apt-get update
sudo apt-get install build-essential libssl-dev

// nvm 설치
curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh -o install_nvm.sh
bash install_nvm.sh
source ~/.profile
nvm install v8.11.1

// Go 설치
curl -O https://storage.googleapis.com/golang/go1.11.2.linux-amd64.tar.gz

// 압축 풀기
tar -xvf go1.11.2.linux-amd64.tar.gz

// 압축 해제를 통해 얻은 go 디렉토리를 /usr/local 경로로 이동
sudo mv go /usr/local

// /usr/local/go/bin/go 디렉토리에 대한 링크(바로가기)를 /usr/local/bin/go에 연결
sudo ln -s /usr/local/go/bin/go /usr/local/bin/go
gedit ~/.profile

// 환경 변수 추가
export GOPATH=$HOME/go
export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
source ~/.profile
```
  
