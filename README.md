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
