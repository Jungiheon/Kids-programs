# 초2 체험·영어 프로그램

광장동 자차 20분 생활권(광진·송파·강동·구리)의 초2 체험·영어 프로그램을 한 화면에서 보고
각 기관 신청 페이지로 바로 넘어가는 모바일 웹앱입니다.

## 구성

- `index.html` — 화면 (필터·검색·카드 렌더링)
- `data.json` — 프로그램 목록 (여기만 고치면 화면이 갱신됩니다)
- `manifest.json`, `apple-touch-icon.png` — 홈 화면에 추가했을 때 앱처럼 보이도록 하는 설정

## 갱신 방법

1. `data.json`의 `meta.updated_label`을 확인 시각으로 바꿉니다.
2. `programs` 배열에서 마감된 항목은 지우고, 새 프로그램은 아래 형식으로 넣습니다.

```json
{
  "id": "기관-강좌번호",
  "status": "open",              // open = 지금 신청가능 / upcoming = 오픈 예정
  "title": "강좌명",
  "short": "배너에 쓸 짧은 이름",
  "org": "기관명",
  "field": "english",            // english(영어 특화) / experience(체험·작가·과학)
  "district": "강동",             // 광진 / 송파 / 강동 / 구리
  "weekend": true,               // 수업이 토·일인지
  "days": "토",
  "schedule": "11/28(토) 14:00~15:30",
  "target": "초2~4",
  "fee": "무료",
  "seat_label": "잔여 11석",       // open일 때 배지에 표시
  "seat_detail": "신청 19/30",
  "registration": "접수 ~11/26 18:00",
  "note": "정회원 필수 등 주의사항",
  "opens_at": null,              // upcoming이면 "2026-11-20T10:00:00+09:00"
  "opens_label": null,           // upcoming이면 "11/20(금) 10:00"
  "url": "https://...",
  "date_start": "2026-11-28"     // 수업 첫날 (정렬용)
}
```

3. `git add -A && git commit -m "11/19 업데이트" && git push` 하면 GitHub Pages에 1분 안에 반영됩니다.

## 개인정보

공개 저장소이므로 아이 이름·연락처·주소·도서관 아이디 같은 개인정보는 넣지 않습니다.
지역은 "광장동 자차 20분 생활권", 대상은 "초2"로만 표기합니다.
