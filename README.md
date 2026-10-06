# 정타버스

외지주와 독립적으로 실행하는 DM 공지·회의·후원 봇입니다. 기존 설정, 토큰, 후원 기록은 복사하지 않았습니다.

## 처음 실행 (PowerShell)

```powershell
cd "정타버스 코드를 저장한 폴더 경로"
py -3.12 -m venv .venv
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
if (!(Test-Path -LiteralPath .env)) { Copy-Item .env.example .env }
notepad .env
python bot.py
```

.env의 JEONGTABUS_TOKEN에 새 정타버스 봇 토큰을 넣고 저장합니다. 토큰은 채팅·GitHub에 공유하지 마세요. 이후에는 가상환경 활성화 후 `python bot.py`로 실행합니다.

Discord 개발자 설정에서 새 봇의 Server Members Intent를 켜고, 봇과 슬래시 명령어 권한으로 서버에 초대하세요. 사용할 채널 읽기·쓰기·이전 메시지 읽기와 역할 관리 권한을 부여하고, 봇 역할을 부여 대상 역할보다 위에 둡니다.

## 기능

- /공지: 내용 입력창 → DM 공지, 제목 [정타버스 공지]
- /관리자, /예외설정, /예외목록: 정타버스 자체 권한과 예외 관리
- 회의방·공지방·로그방·사유방 등록, 회의 공지·시작·종료, 불참 사유, 미참여자·잠수 확인
- 회의 미참여자 경고 및 경고 역할 관리
- 후원 공지·랭킹 양식, 후원 기록·차감·삭제·목록, 금액별·순위별·공통 후원자 역할
- 역할 닉네임 기능은 포함하지 않습니다.

설정과 기록은 이 폴더의 jeongtabus.sqlite3에 처음 실행 시 생성합니다. 외지주의 데이터베이스를 복사하거나 공유하지 마세요. 이 파일을 보존해야 재시작 후에도 기록이 남습니다.

호스팅할 경우 기존 봇 서버가 아닌 별도 서버를 사용하세요. 시작 파일은 bot.py, 환경변수 이름은 JEONGTABUS_TOKEN입니다. 저장소는 https://github.com/yoohuij/jungta 이며, 호스팅 배포와 토큰 등록은 별도로 진행합니다.
