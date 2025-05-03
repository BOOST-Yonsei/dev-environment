# webOS 컴종설 프로젝트 개발환경 세팅

## webOS 빌드 환경

1. docker + docker compose 설치
2. `webOS-build` 폴더 복제
3. `webOS-build/docker/` 폴더 생성
	- 외장하드 등 다른 장치로 가리키는 symlink도 가능
4. `webOS-build/run.sh` 실행하면 `Ubuntu 22.04` 환경 쉘 준비완료
	- 데스크탑 Ubuntu와 다르게 많은 패키지가 빠진 상태
	- username = `ubuntu`
	- password = `<없음>`
	- 3번에서 생성한 `docker` 폴더가 `Ubuntu` 컨테이너 안에서 홈 경로
		- 그 외의 경로 및 파일은 휘발성

## webOS 시리얼 통신

[picocom](https://github.com/npat-efault/picocom)을 추천한다.

라즈베리파이가 켜지기 이전에 먼저 USB를 연결하고 picocom으로 콘솔에 접속한 상태에서 부팅을 시작하면 된다.

```sh
ls /dev/tty* | grep -i usb # -> USB 시리얼 콘솔의 장치경로 확인
sudo picocom -b 115200 /dev/<ttyUSB0>
# -g <로그파일 경로> 옵션을 추가하면 콘솔 데이터를 파일로 저장할 수 있다
```

부팅 로그가 끝난 뒤에 `Enter`키를 치면 콘솔 로그인 프롬프트가 나올 것이다. [참고자료](https://www.webosose.org/docs/iot/setup/setting-up-network-iot/#setting-up-serial-connection)
