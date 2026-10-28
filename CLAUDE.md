# sadaritrip.com 사이트 저장소

사다리트립 무료 베타 웹사이트예요. `main`에 push하면 Cloudflare Workers Builds가 sadaritrip.com에 자동 배포해요(`wrangler.jsonc`, 빌드 명령 없음, `dist/` 그대로 배포). sadaritrip.co.kr은 같은 사이트로 연결하고 페이지가 sadaritrip.com으로 넘겨요.

## 규칙 (대표 제니 님 지시)
- 앱을 바꾸는 일(기능·디자인·문구·데이터)은 제니 님 승인 뒤에만 해요. 원본은 Claude 아티팩트 https://claude.ai/artifact/Uc3gcV9eUVgVj3v46Vy5gz (사다리트립 사업부가 관리).
- 무료 베타: 결제·예약을 받지 않아요(돈을 받으면 여행업 등록·통신판매업 신고가 먼저예요).
- 여행지 비용은 출처 있는 추정치, 지어낸 데이터 금지, 개인정보 수집 금지.
- 비밀번호·토큰·서명 키는 저장소에 넣지 않아요.

## 아티팩트 → 사이트 반영
1. Artifact 도구 `action: "read"`로 위 아티팩트를 읽어 저장된 HTML을 받아요.
2. 그 HTML로 `dist/index.html`을 바꾸되, 맨 앞 `<head>`의 사이트 전용 부분(lang, .co.kr → .com 이동 스크립트, 설명·og 메타, theme-color, 아이콘)은 그대로 유지해요.
3. commit 후 `git push origin main`, 2~3분 뒤 https://sadaritrip.com 확인.
