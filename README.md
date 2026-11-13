# 굿즈 발매 캘린더 — GitHub Pages 설치 방법

## 파일 구성
- `index.html` — 회원용 달력 페이지 (월별 일정, 종류·판매처 필터, 검색, 진행 중 팝업)
- `admin.html` — 관리자 페이지 (일정·판매처·판매 상품·팝업 등록/수정/삭제 → 게시)
- `data.json` — 모든 일정 데이터 (예시 3개 포함, 관리자 페이지에서 지우면 됨)
- (스타일·스크립트는 html 안에 포함되어 있어 별도 폴더 없음)

## 1. 저장소 만들고 올리기
1. GitHub에서 새 저장소 생성 (예: `goods-calendar`, **Public**)
2. `index.html`, `admin.html`, `data.json` 3개를 저장소 맨 위(루트)에 업로드 (Add file → Upload files)
   - 내 PC에서 `index.html`을 더블클릭해 열면 일정이 안 불러와져요. 꼭 GitHub Pages 주소로 확인하세요.
3. Settings → Pages → Branch: `main` / `(root)` → Save
4. 1~2분 뒤 `https://아이디.github.io/goods-calendar/` 에서 확인

## 2. 관리자 토큰 만들기 (한 번만)
1. GitHub → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token
2. Repository access: **Only select repositories** → `goods-calendar` 만 선택
3. Permissions → Repository permissions → **Contents: Read and write**
4. 만료일 설정 후 생성 → `github_pat_...` 복사

## 3. 관리자 페이지 사용
1. `https://아이디.github.io/goods-calendar/admin.html` 접속
2. [GitHub 연결 설정]에 아이디 · 저장소 이름 · 토큰 입력 → **저장하고 불러오기**
3. [판매처 관리]에서 판매처 먼저 등록 → [일정 관리]에서 일정 등록
4. 다 끝나면 오른쪽 위 **사이트에 게시** → 약 1분 뒤 반영

## 보안 메모
- admin.html 주소는 누구나 열 수 있지만, **토큰이 없으면 보기만 되고 수정·게시는 불가**해요.
- 토큰은 입력한 브라우저에만 저장돼요. 공용 PC에서는 사용 후 [연결 해제].
- 관리자를 여러 명 두려면 각자 저장소 Collaborator로 초대하고 본인 토큰을 만들게 하면 돼요.
- 토큰 없이 쓰고 싶다면: 관리자 페이지에서 작업 → [data.json 다운로드] → GitHub에 직접 업로드해도 됩니다.

## 일정 종류
발매 · 예약판매 · 추첨·응모 · 팝업스토어 · 재입고 · 기타
(바꾸려면 `assets/common.js`의 `TYPES` 수정)

## 일정 공유 링크
일정을 클릭하면 주소가 `.../#e=일정ID` 로 바뀌어요. 이 링크를 카페에 올리면 바로 해당 일정 상세가 열려요.
