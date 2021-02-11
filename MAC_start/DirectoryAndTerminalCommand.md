목차
macOS 터미널 사용을 위한 디렉토리 구조 및 기본 명령어
1. macOS 디텍토리 구조  
1.1 표준 디텍토리  
1.2 UNIX 고유 디텍토리
2. macOS 기본 명령어

디렉토리 = 폴더  
# macOS 터미널 사용을 위한 디렉토리 구조 및 기본 명령어
## 1. macOS 디렉토리 구조
[참고 사이트 1](https://xho95.github.io/macos/file-system/directory/2016/10/09/macOS-Directory-Structure.html)  
[참고 사이트 2](https://difyel.com/apple/macos/macos-directory-structure/#Standard_folders)  
<img src="https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/art/mosx_fs_layout_2x.png" height="600">  
로컬, 시스템 및 사용자 도메인이 macOS 설치의 로컬 파일 시스템에 매핑되는 방법을 보여줍니다.  
(네트워크 도메인은 표시되지 않지만 여러면에서 로컬 도메인과 유사합니다.)이 그림은 사용자가 볼 수있는 표시되는 디렉토리를 보여줍니다.  
사용자의 시스템에 따라 다른 디렉토리가 표시되거나 여기에 표시된 디렉토리 중 일부가 숨겨 질 수 있습니다.  
- / : 루트 디렉토리  
- System domain : 시스템에 관련된  응용 프로그램 자원이 포함된다.  
시스템 도메인은 애플에 의해 설치된 시스템 소프트웨어가 포함되어 있습니다.  
시스템 도메인의 리소스는 시스템을 실행하는 데 필요합니다.  
사용자는이 도메인에서 항목을 추가, 제거 또는 변경할 수 없습니다.

 - User domain : 각 사용자와 관련된 파일, 응용프로그램, 자원을 포함하는 사용자 디렉토리들을 포함하는 영역.     
기술적으로 모든 사용자를 포함하지만이 유저 도메인은 런타임시 현재 사용자의 홈 디렉토리 만 반영합니다.  
사용자 홈 디렉토리는 컴퓨터의 부트 볼륨 ( /Users디렉토리에 있음) 또는 네트워크 볼륨에있을 수 있습니다.  
권한에 관계없이 각 사용자는 각자 자신의 홈 디렉토리에있는 파일에 액세스하고이를 제어 할 수 있습니다.  
 - Local domain : 현재 컴퓨터에서 공유되는 응용 프로그램이나 파일, 자원등이 포함됩니다.  
단일 물리적 디렉토리에 해당하지 않고 대신 로컬 부트 (및 루트) 볼륨의 여러 디렉토리로 구성됩니다. (어플리케이션, 라이브러리 디렉토리 ...).  
이 도메인은 일반적으로 시스템에서 관리하지만 관리 권한이있는 사용자는이 도메인에서 항목을 추가, 제거 또는 수정할 수 있습니다.  
 - Network domain : 네트워크 도메인은 로컬 영역 네트워크의 모든 사용자가 공유하는 응용 프로그램 및 문서와 같은 자원이 포함되어 있습니다.  
이 도메인의 항목은 일반적으로 네트워크 파일 서버에 있으며 네트워크 관리자가 제어합니다.  

도메인 이외에 표준 디텍토리와 UNIX 고유 디텍토리로도 구분한다.  
### 1.1 표준 디텍토리
첫 글자가 대문자로 표시되고, Finder에서 확인 가능한 디렉토리들.  
Applications local domain으로 분류. 컴퓨터의 모든 사용자가 사용할 앱을 설치하는 곳. 하위디렉토리중 하나인 Utilites는 로컬 시스템 관리에 사용하기 위한 디렉토리.
Library 캐시파일, 리소스 등 응용프로그램과 관련된 정보를 포함. 각 도메인 또는 특정 사용자와 연결된다.  
[자세한 설명](https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/MacOSXDirectories/NaN)
local domain, 시스템 폴더, 사용자별로 각각 존재.
Network LAN컴퓨터 목록 포함.
System system domain으로 분류.macOS에 필요한 시스템 리소스가 포함된다. apple에서 제공하는 디렉토리이며, 수정되어서는 안된다.
Users user domain으로 분류. 각 사용자와 관련된 파일이 저장된다. 내부에 여러 디렉토리를 포함하며, public이외에는 다른 사용자의 디렉토리에 접근할 수 없다.  
아래의의 디렉토리는 사용자 문서 및 미디어 저장 전용입니다. 사용자가 명시 적으로 지시하지 않는 한 앱은 이전 디렉토리에 파일을 쓰면 안됩니다.
(Users/사용자명/에 포함된 디렉토리 들이다)
Applications-사용자 별 앱이 포함되어 있습니다.
Desktop-사용자의 데스크탑에있는 항목을 포함합니다.
Documents-사용자 문서 및 파일이 포함됩니다.
Downloads-인터넷에서 다운로드 한 파일이 포함되어 있습니다.
Library-사용자 별 앱 파일을 포함합니다 (macOS 10.7 이상에서는 숨김).
Movies-사용자의 비디오 파일이 포함됩니다.
Music-사용자의 음악 파일이 포함되어 있습니다.
Pictures-사용자의 사진이 포함됩니다.
Public-사용자가 공유하려는 콘텐츠가 포함되어 있습니다.
Sites-사용자의 개인 사이트에서 사용하는 웹 페이지를 포함합니다. (이러한 페이지를 표시하려면 웹 공유를 활성화해야합니다.)

### 1.2 UNIX 고유 디텍토리
첫 글자가 소문자로 표시되고, Finder에서 확인할 수 없는 디렉토리들.  
일반적인 사용자가 필요하지 않은 파일에 접근하지 못하게 숨겨져있다.  

## 2. macOS 기본 명령어
[참고 사이트 1](https://jisuhan.tistory.com/entry/%EC%BB%B4%ED%93%A8%ED%84%B0-%EA%B5%AC%EC%A1%B0-MIPS-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC)  
[참고 사이트 2](https://haloaround.tistory.com/7)
### 2.1 디렉토리 관련 명령어(목록, 생성, 제거
### 2.2 파일 관련 명령어
### 2.3 프로그램 컴파일등등 관련 명령어
