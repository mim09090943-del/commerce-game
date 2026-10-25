# BLUE MARKET — GitHub + Render 배포 안내

이 프로젝트는 Node.js + Express + Socket.IO 웹 서비스입니다. GitHub에 코드를 올린 뒤 Render에서 실행할 수 있도록 `render.yaml`을 포함했습니다.

## 1. ZIP 압축 풀기
`blue_market_complete` 폴더 안에 `package.json`, `server.js`, `public/`, `render.yaml`이 있는지 확인합니다.

## 2. GitHub 저장소 만들기
1. GitHub에 로그인하고 **New repository**를 누릅니다.
2. 저장소 이름을 `blue-market`처럼 정하고 저장소를 만듭니다.
3. 압축 해제한 프로젝트 폴더 안의 파일을 저장소 루트에 업로드합니다. `package.json`과 `server.js`가 저장소 첫 화면에 보여야 합니다.
4. `node_modules`와 `game-save.json`은 업로드하지 않습니다.

## 3. Render에 연결
1. Render에 로그인한 뒤 **New + → Blueprint**를 선택합니다.
2. 방금 만든 GitHub 저장소를 연결합니다.
3. Render가 `render.yaml`을 읽어 서비스를 생성하도록 진행합니다.
4. 환경변수 `ADMIN_PIN` 값을 설정합니다. 기본 암호를 유지하려면 `0403`을 입력합니다.
5. 배포가 완료되면 Render가 제공하는 `https://...onrender.com` 주소로 접속합니다.

## 4. 운영할 때 중요
- 이 설정은 게임 저장 파일을 `/var/data/game-save.json`에 저장하도록 영구 디스크를 설정합니다. Render의 영구 디스크는 유료 플랜/요금이 적용될 수 있으므로 생성 화면에서 가격을 확인하세요.
- 실시간 게임은 서버 인스턴스 하나만 사용하세요. 여러 인스턴스를 켜면 각 서버의 게임 상태가 서로 달라질 수 있습니다.
- 배포 후 별도의 휴대폰/브라우저 2~3개로 접속·매수·매도·턴 진행·뉴스 전달·재접속을 먼저 테스트하세요.
- 링크를 가진 사람이 접속할 수 있으므로 게임이 끝난 뒤에는 관리자 암호를 바꾸거나 서비스를 중지하세요.
- `.env`, 관리자 암호, 저장 파일을 GitHub에 올리지 마세요.

## 로컬에서 먼저 실행
Node.js 18 이상 설치 후 터미널에서 프로젝트 폴더로 이동해 실행합니다.

```bash
npm install
npm start
```

그 다음 `http://localhost:3000`을 엽니다.
