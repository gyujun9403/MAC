## 1. vim개요와 모드
vim은 유닉스 및 유닉스 기반 OS에서 주로 사용하면 텍스트 편집기이다.  
모드 별로 텍스트를 편집/뷰/제어하는 기능이 구분되어 있고, 모든 명령을 키보드를 통해 수행할 수 있다.  

이미지 참고 https://m.blog.naver.com/nfwscho/220351071053  
![vim 모드](https://user-images.githubusercontent.com/75626815/107260717-bf6f4d00-6a81-11eb-8e05-be2ae8ac933a.png)
모드에 대한 설명  
  
### 1.1 일반모드
처음 vim을 실행했을때, 편집모드/비주얼모드에서 ESC를 입력했을 때, 명령라인 모드에서 Enter을 눌렸을때 진입한다.  
찾기, 커서이동, 다른 모드로 넘어가기 위한 교두보 역할, 텍스트 편집(텍스트 입력X)을 수행한다.
  
### 1.2 편집 모드(입력모드)  
일반 모드에서 입력명령(i, I, a, A, o, O, s, S)을 입력하여 진입한다.
진입한 이후 해당 커서위치를 기반으로 텍스트(내용)를 입력할 수 있다.
  
### 1.3 명령라인 모드  
일반모드에서 :을 입력하여 진입한다. 
진입한 이후 텍스트 파일을 대상으로 한 치환, 저장, 종료, vim설정 등의 대부분 제어 작업 수행한다.
  
### 1.4 비주얼 모드  
v, V, ctrl, q를 조합하여 진입한다.
텍스트에서 범위을 지정하고, 편집할 수 있다(텍스트 입력X).
  #### 1.4.1 비주얼 모드
  일반 모드에서 v(소문자)를 통해 진입한다.
  현재 커서부터 시작하여 글자(텍스트)단위로 커서의 범위를 지정할 수 있는 모드이다.
  (워드나 한글등에서 마우스로 블럭지정하는것과 같다.)
  #### 1.4.2 비주얼 라인 모드
  일반 모드에서 V(대문자)를 통해 진입한다.
  u j를 통해 위 아래로 한 줄씩 블럭을 지정한다.
  #### 1.4.3 비주얼 블럭 모드
  일반 모드에서 ctl-v(at macOS)를 통해 진입한다.
  이건 직접 보는걸 추천... 중간부분만 복사할 수 있는 능력을 지님.  
  
  
## 2. 모드 별 명령어  
### 2.1 커서 및 화면 이동(at 일반 모드, 비주얼 모드)
#### 2.1.1 기본 및 단어 이동  
| 설명 | 단축키 | 설명 | 단축키 |
| :---------- | :---------: | :---------- | :----------: |
|왼우상하| hjkl|||
|→첫 글자 |w| →마지막 글자|e|
|←첫 글자 |b| ←마지막 글자|ge|
#### 2.1.2문장 내 이동  
| 설명 | 단축키 | 설명 | 단축키 |
| :---------- | :---------: | :---------- | :----------: |
|줄의 처음|0|줄의 마지막|$|
|문장의 처음|^||

#### 2.1.3문서 내 이동  
| 설명 | 단축키 | 설명 | 단축키 |
| :---------- | :---------: | :---------- | :----------: |
|문서 처음|gg|문서 마지막|G|  

#### 2.1.4 괄호 이동
| 설명 | 단축키 | 설명 | 단축키 |
| :---------- | :---------: | :---------- | :----------: |
|이전구절|&#93;&#93;|다음구절|&#91;&#91;|  
|현재 괄호의 짝으로 이동|&#37; |||

#### 2.1.5 화면스크롤(at 일반 모드, 비주얼모드)  
| 설명 | 단축키 | 설명 | 단축키 |
| :---------- | :---------: | :---------- | :----------: |
|한 화면 앞|ctrl f(forward)|한 화면 아래|ctrl f(backword)|
|반 화면 앞|ctrl u(up)|반 화면 아래|ctrl d(down)|

| 설명 | 단축키 |
| :---------- | :---------: |
|현재 화면 맨 위 |shift h|
|현재 화면 중간 |shift m|
|현재 화면 아래 |shift l|

### 2.2 편집 진입(at 일반 모드 → 편집 모드)
| 설명 | 단축키 |
| :---------- | :---------: |
|현재 커서위치에서 삽입 시작|i|
|현재 줄 처음위치에 삽입 시작|I|
|아래에 새로운 줄|o|
|위에 새로운 줄|O|

### 2.3 명령 라인모드 진입
| 설명 | 단축키 |
| :---------- | :---------: |
|명령 라인모드 진입|:|
|저장|:w|
|파일명으로 저장|:w 파일명.확장자|
|현재 문서 닫기|:|
|저장후 닫기|:wq|
|저장하지 않고 닫기|:q!|
추가 지금 파일 저장 및 vim종료 : ZZ

### 2.4 일반 모드에서의 편집(복사, 삭제, 붙이기, 들여쓰기(여러행))
| 설명 | 단축키 |
| :---------- | :---------: |
|블럭/커서 잘라내기|x|
|현재커서부터 단어 마지막까지 잘라내기|dw|
|한 줄 잘라내기|dd|
|블럭/커서 복사하기|y|
|현재 커서부터 단어 마지막까지 복사|yw|
|한 줄 복사하기|yy|
|붙여넣기|p|
|숫자번 만큼 붙여넣기 숫자|p|
|커서가 위치한 문자 잘라내고 삽입|s|
(단어는 커서 다음, 행은 커서 다음줄)

### 2.5 비주얼 모드에서의 편집(복사, 삭제, 붙이기)
비주얼모드의 경우 커서를 통한 블럭 지정이 목적이다.
| 설명 | 단축키 |
| :---------- | :---------: |
|지정된 블럭 복사|y|
|지정된 블럭에 붙여넣기|p|
|지정된 블럭 삭제|d|
|현재 라인 삭제|dd|

## 3. 자주쓰는 기능 순서
여러 행 들여쓰기

Ref  
https://gracefulprograming.tistory.com/30  