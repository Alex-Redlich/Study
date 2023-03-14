# Django 시작하기

1. 프로젝트를 위한 폴더를 생성한다.
    1. `mkdir 프로젝트 폴더명`
    
2. 프로젝트 폴더를 우클릭하여 vscode 로 열어준다.
    
    
3. `.gitignore` 파일을 생성한다.
    1. `touch .gitignore` : 터미널 명령어 → git bash 창에서 작업을 한다면
    2. [gitignore.io](http://gitignore.io) 에서 `visualStudioCode`, `python`, `django` 를 선택해서 복붙한다.
    
4. 가상환경을 설정한다.
    1. `python -m venv venv` ⇒ “python -m venv 가상환경폴더명” 형태 (폴더명 : venv 권장)ve
    
5. 가상환경 활성화
    1. `source venv/Scripts/activate` : source v 탭 s 탭 a 탭
    2. Mac 에서는 (venv/Bin/activate)
    3. 활성화가 되었다면 상단에 `(venv)` 확인
    4. 추가로 `pip list` 를 통해서 정상적으로 생성되었는지 확인
        1. 설치된 패키지들이 없으면 정상
        2. 설치한 것이 없음에도 패키지들이 많이 있다면 venv 폴더 삭제 후 다시 가상환경 설정
        
6. 장고를 설치한다. (필요한 패키지를 설치한다.)
    1. `pip install django==3.2` 
    2. 만약 `requirements.txt` 가 제공된다면
        1. `pip install -r requirements.txt`   → 기억 필수
        
7. `requirements.txt` 파일을 생성한다.  (잊지말자!)
    1. 패키지의 목록을 버전과 함께 작성해두는 파일
    2. `pip freeze > requirements.txt`
    
8. 모든 설치가 끝났으니 프로젝트를 생성하자
    1. `django-admin startproject 프로젝트명 .`
        1. 마지막에 `.` 이 있는 경우는 현재 폴더에 바로 파일을 생성
        
        2. `.` 이 없으면 프로젝트명으로 폴더를 만들고 그 내부에 파일을 생성
        
9. 장고 application을 생성한다.
    1. `python [manage.py](http://manage.py) startapp 앱이름`
        1. 앱이름은 복수형으로 작성하는 것을 권장
    2. `[settings.py](http://settings.py)` 내부에 방금 생성한 앱을 등록해야한다.
        1. `INSTALLED_APP` 리스트 내부에 어플리케이션 이름을 문자열형태로 등록해준다.
        2. 주의) `,` 빠지지 않도록 신경을 써주세요!!!