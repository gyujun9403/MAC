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
###### <img src="https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/art/mosx_fs_layout_2x.png" height="600"> <br> 이 그림은 사용자가 볼 수있는 표시되는 디렉토리를 보여줍니다. (네트워크 도메인은 표시되지 않지만 여러면에서 로컬 도메인과 유사합니다.)<br>사용자의 시스템에 따라 다른 디렉토리가 표시되거나 여기에 표시된 디렉토리 중 일부가 숨겨 질 수 있습니다.
- \ : 루트 디렉토리  
- **System domain**  
시스템에 관련된  응용 프로그램 자원이 포함되는 영역(도메인)입니다.  
시스템 도메인은 애플에 의해 설치된 시스템 소프트웨어가 포함되어 있으며, 이곳의 리소스는 시스템을 실행하는 데 필요합니다.  
사용자는 이 도메인의 항목을 추가, 제거 또는 변경할 수 없습니다.

 - **User domain**  
각 사용자와 관련된 파일, 응용프로그램, 자원을 포함하는 사용자 디렉토리들을 포함하는 영역입니다.     
기술적으로 유저 도메인은 모든 사용자를 포함하지만이 런타임시 현재 사용자의 홈 디렉토리에만 접근할 수 있습니다.  
각 사용자는 각자 자신의 홈 디렉토리에있는 파일에 자유롭게 액세스하고 이를 제어 할 수 있습니다.  
사용자 홈 디렉토리는 컴퓨터의 부트 볼륨 ( /Users디렉토리) 또는 네트워크 볼륨에있을 수 있습니다.  

 - **Local domain**  
 현재 컴퓨터에서 공유되는 응용 프로그램이나 파일, 자원등이 포함됩니다.  
 로컬 부트 (및 루트) 볼륨의 여러 디렉토리로 구성됩니다. (어플리케이션, 라이브러리 디렉토리 ...).  
 이 도메인은 일반적으로 시스템에서 관리하지만, 관리 권한이있는 사용자는 이 도메인에서 항목을 추가, 제거 또는 수정할 수 있습니다.  

 - **Network domain**  
 로컬 영역 네트워크의 모든 사용자가 공유하는 응용 프로그램 및 문서와 같은 자원이 포함되어 있는 영역입니다.  
 이 도메인의 항목은 일반적으로 네트워크 파일 서버에 있으며 네트워크 관리자가 제어합니다.  

도메인 이외에 표준 디텍토리와 UNIX 고유 디텍토리로도 구분한다.  
### 1.1 표준 디텍토리
첫 글자가 대문자로 표시되고, Finder에서 확인 가능한 디렉토리들.  
 - "\Applications"  
 local domain으로 분류. 컴퓨터의 모든 사용자가 사용할 앱을 설치하는 곳이다.  
 하위디렉토리중 하나인 Utilites는 로컬 시스템 관리에 사용하기 위한 디렉토리이다.
 - "\Library"  
 캐시파일, 리소스 등 응용프로그램과 관련된 정보를 포함. 각 도메인 또는 특정 사용자와 연결된다.  
[자세한 설명](https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/MacOSXDirectories/NaN)
 - "\local domain"  
 시스템 폴더, 사용자별로 각각 존재. Network LAN컴퓨터 목록 포함.  
 
 - "\System"  
 system domain으로 분류. macOS에 필요한 시스템 리소스가 포함된다.  
 apple에서 제공하는 디렉토리이며, 수정되어서는 안된다.
 - "\Users"  
 user domain으로 분류. 각 사용자와 관련된 파일이 저장된다.  
 내부에 여러 디렉토리를 포함하며, public이외에는 다른 사용자의 디렉토리에 접근할 수 없다.  
 아래의의 디렉토리들은 \Users 내부의 사용자 문서 및 미디어 저장 전용입니다.  
 사용자가 명시 적으로 지시하지 않는 한 앱은 이전 디렉토리에 파일을 쓰면 안됩니다.  
 (Users/사용자명/에 포함된 디렉토리 들이다)  
    - Applications-사용자 별 앱이 포함되어 있습니다.
    - Desktop-사용자의 데스크탑에있는 항목을 포함합니다.
    - Documents-사용자 문서 및 파일이 포함됩니다.
    - Downloads-인터넷에서 다운로드 한 파일이 포함되어 있습니다.
    - Library-사용자 별 앱 파일을 포함합니다 (macOS 10.7 이상에서는 숨김).
    - Movies-사용자의 비디오 파일이 포함됩니다.
    - Music-사용자의 음악 파일이 포함되어 있습니다.
    - Pictures-사용자의 사진이 포함됩니다.
    - Public-사용자가 공유하려는 콘텐츠가 포함되어 있습니다.
    - Sites-사용자의 개인 사이트에서 사용하는 웹 페이지를 포함합니다.  (이러한 페이지를 표시하려면 웹 공유를 활성화해야합니다.)

### 1.2 UNIX 고유 디텍토리
첫 글자가 소문자로 표시되고, Finder에서 확인할 수 없는 디렉토리들.  
일반적인 사용자가 필요하지 않은 파일에 접근하지 못하게 숨겨져있다.  

## 2. macOS 터미널 기본 명령어
[참고 사이트 1](https://jisuhan.tistory.com/entry/%EC%BB%B4%ED%93%A8%ED%84%B0-%EA%B5%AC%EC%A1%B0-MIPS-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC)  
[참고 사이트 2](https://haloaround.tistory.com/7)  
[관련 Apple 아카이브](https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html#//apple_ref/doc/uid/TP40010672-CH2-SW7)  
자세한 옵션 및 예제는 링크에 더 잘 나와있다. 여기서는 사용가능한 기능만 명시한다.  
.현재 디렉토리  
..부모 디렉토리  
/최상위 디렉토리   
~홈 디렉토리  
절대 및 상대 디렉토리에 대한 설명  
&#91;&#93;    
### 2.1 디렉토리 관련 명령어(목록, 생성, 제거)
|내용|내용|옵션 및 기타|
|---|---|---|
|현재 dir의 <br>절대 경로 출력|pwd|
|해당 dir의 <br>file 및 dir 목록 출력|ls &#91;&#8211;adlR&#93; &#91;DIR&#93;|a 모든파일 출력<br>l 세부 정보 출력<br>F 파일의 형태 출력<br>t 최근 생성순 출력<br>h 사람이 보기 쉽게|
|해당 dir로 <br>커서 이동|cd DIR||  
|해당 위치에 <br>dir 만들기|mkdir DIR|p 상위 디렉토리가 없는 경우 같이 생성(???)|  
|해당 위치에서 <br>빈 dir 전부 삭제.|rmdir &#91;DIR&#93;|p 제거된 디렉토리에 대한 메시지 표시<br>s 표시되지 않음<br>부모까지 빈 경우 전부 삭제 가능|
|dir 이름 변경|mv &#91;&#8211;i&#93; &#91;이전DIR&#93; &#91;새DIR&#93;|근데 내부에 파일이 있으면?| 
|dir 복사|cp &#91;&#8211;ri&#93; &#91;원본DIR&#93; &#91;옮길DIR&#93;|a 모든 권한까지 복사<br>i 덮어쓰기 전에 물어봄<br>r DIR 하위 내용까지 번부 복사<br>v 완료시 메세지<br>u 최신버전만 복사|


### 2.2 파일 관련 명령어
|내용|내용|옵션 및 기타|
|---|---|---|
|파일 형식 확인|file FILE|
|파일명 변경|mv &#91;이전파일명&#93; &#91;새파일명&#93;|  
|파일 이동|mv &#91;파일명&#93; &#91;디렉토리&#93;|f 덮어쓰기<br>i 덮어쓰기 할때 물어봄<br>f 이동과정 보여줌|  
|파일 제거|rm &#91;&#8211;fri&#93; &#91;파일명&#93;|f 삭제할때 확인x<br>r 디렉토리 삭제<br>rf 디렉토리 안의 모든 내용물도 같이 삭제 + 안물어봄.|  
|파일 생성|touch FILE|  
|파일/내용 정렬|sort &#91;&#8211;trbfn&#93;|기본 오름차순<br>r 역순 출력<br>kN N번째 필드를 기준으로 정렬<br>u 중복제거<br>f 대소문자 구분 안함|  
|파일 출력|cat &#91;&#8211;fri&#93; &#91;FILE&#93;|간단하게 짧은 문서 출력에 용이<br>n 빈행 포함 행번호 추가해서 출력<br>cat을 통한 파일만들기 가능|  
|파일에<br>줄번호 붙여 출력|nl FILE|  
|파일 출력|more less FILE|less, more는 쉽게 생각하면 뷰어로 생각.<br>mere은 아래방향으로만 이동하면서 읽음<br>ls 옵션 DIR 	&#124;more로 자주 사용.<br>less의 경우 상하이동가능하며 화살표 Page Up Down이용 가능<br>나가기위해서는 q입력.|  
|파일내 패턴을 찾기|grep &#91;옵션&#93; patten FILE|c 일치하는 줄의 수 출력<br>i 대소문자 구별안함<br>n 일치하는 줄의 번호도 출력<br>v 일치하지 않는 줄 출력|  
|조건을 충족하는 <br>파일을 찾아 출력|find 위치 고전 명령|... 이건 사이트 찾아서 링크|






