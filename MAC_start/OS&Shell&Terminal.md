Shell = 셸(표준어) = 쉘(문화어). 실제 발음해보면 쉐(짧게)옐(길게) 발음

## 1. OS, Shell, Terminal의 관계
![IMG](https://i.imgur.com/nz3UXlY.png)
https://jinshine.github.io/2018/05/10/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B8%B0%EC%B4%88/%EC%BB%A4%EB%84%90(Kernel)%EA%B3%BC%20%EC%89%98(Shell)/
OS는 컴퓨터의 HW관리, 성능향상, 편의성을 제공하는 시스템이다.
Kernel은 OS에서 실제로 HW를 관리하는 OS의 기능이며, OS의 상당 부분을 차지하고 있다.
Shell은 OS의 테두리에서 사용자에게 인터페이스를 제공하는 소프트웨어(프로그램)이다. 사용자의 명령을 해석하여 커널로 보내고, 커널의 명령을 번역하여 사용자에게 보여준다.
Shell Script는 Shell에서 실행하고자하는 명령을 텍스트파일로 저장한 명령의 모음이다. .sh확장자명을 가진다.
Terminal은 사용자의 명령을 입력받아 Shell에 전달하거나, Shell의 인터페이스를 사용자에게 보여주는 통로와 같은 sw이다. CLI방식을 사용한다.
이때, 콘솔은 로컬장치에서 직접 명령어를 장치를 작성할 수 있는 SW 혹은 물리적 입출력 장치이며, 
Terminal은 콘솔과 달리 로컬뿐만이 아니라 원격으로 접속할 수 있는 SW이다.

## Shell이 수행하는 기능
 - 명령어 해석 기능.  
 사용자와 커널 사이의 명령을 해석해서 전달한다.
 - 프로그래밍 기능  
 이때 셸로 작성된 프로그램을 셸 스크립트라고 한다
 - 사용자 환경설정 기능(리눅스 세션의 설정)  
 리눅스 세션에 대한 변수를 정의하여, 사용자가 리눅스 환경을 자신이 완하는 상태로 설정할 수 있게 한다.  
 (셸의 환경변수)
 
 
## Shell의 종류
### bourne shell계열의 셸
 - bourne shell(sh)  
 최초로 개발된 셸. 가장 기본적이며 유닉스 초기부터 사용됨.
 - korn shell(ksh)  
 bourne shell을 확장한 형태. 명령어 히스토리기능, 앨리어스(alias), 작업제어 기능이 추가.  
 일반적으로 유닉스에서 가장 많이 사용되는 셸.
 - bourne-again shell(bash)  
 C shell과 korn shell의 장점을 결합하여 만들었으며, GNU 프로젝트에 의해 만들어지고 배포되었다.  
 리눅스에서 가장 많이 사용되고, macOS의 표준 셸  
 대표 기능 : 탭완성, 명령라인 히스토리, alias, 중괄호 확장 #echo, 반복문, 줄편집, 역 점진 탐색
 https://neul-carpediem.tistory.com/48
 - z shell  
 bash shell의 대부분의 명령어가 호환되며 다양한 기능과 사용성을 제공하는 셸.
 bash에서 호완이 안되는 것?
 
### C 셸 계열의 셸
 - C shell(csh)  
 C언어를 기반으로 만들어진 셸. 프로그램 작성 기능에 특화. 
 - TC Shell(tcsh)  
 확장된 형태의 C Shell

## bash와 zsh의 공통기능
https://sunlightmedia.org/ko/bash-vs-zsh/  


## bash와 zsh의 차이.
https://bit.ly/3tDMhlC  
https://bit.ly/36Us8xN  
1. Aliases 작성 방식 
2. quoting
3. Pipe and subshells
4. Whildcard handling


## Shell 기타
터미널에 표시되는 $는 프롬프트이다. 사용자의 명령을 받아들일 준비가 되었음을 표시해준다.
프롬프트?

## 유닉스 macOS 리눅스 WindowOs
https://bit.ly/2LxBSqo  
(정리가 잘 되어있는데 약간 다른설명도 있는듯 하다. 리눅스는 유닉스의 기능만 따온것이고, macOS는 유닉스의 일부인데 리눅스랑 엮고...)  
역사 요약  
맨 처음 만들어진 근본 OS가 유닉스  
apple에서 만든 유닉스가 macOS(유닉스)  
유닉스에서 기능만 따온것이 리눅스(유닉스 계열=UNIX like)  
리눅스를 대중적으로 쉽게 만든게 우분투 리눅스  
유닉스랑 전혀 상관없이 독자 개발이지만 가장 많이 쓰이는게 WindowOS

##GUI와 CLI에 대한 구분
GUI와 CLI는 유저와의 소통방식, 즉 인터페이스의 차이를 기준에 따른 구분이다.
GUI는 그래픽을 통해 사용자와 소통하는 방식
CLI는 텍스트(커맨드)를 통해 사용자와 소통하는 방식이다. CLI가 GUI에 비해 직관성이 떨어지지만 자원을 적게 소모한다.


참고  
https://jhnyang.tistory.com/57  
https://pliss.tistory.com/91
shell 역사를 알기 좋지만 번역기 돌린듯 : https://bit.ly/36Rth9r
