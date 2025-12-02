    classDef step fill:#fff,stroke:#333,stroke-width:2px,text-align:left,rx:5,ry:5;
    classDef highlight fill:#e1f5fe,stroke:#0277bd,stroke-width:2px,text-align:left,rx:5,ry:5;
    %% 노드 데이터
    Step1["<b>① 기획 설계</b><br/>- 서비스 목적 정의<br/>- 유저 시나리오 / 페르소나<br/>- 정책 / BM 설계<br/>- 기능 정의 및 화면 흐름 설계"]
    Step2["<b>② 데이터 수집(스크래핑) 구조 설계</b><br/>- 소스 선정<br/>- 스크래핑 방식(병합/루프)<br/>- 데이터 포맷 정리(PDF/XML → Binary)"]
    Step3["<b>③ n8n 자동화 파이프라인 구축</b><br/>- 스크래핑 → 이미지 생성<br/>- 이미지 → 영상 생성<br/>- 영상 → 폴더 저장<br/>- (옵션) 유튜브 자동 업로드"]
    Step4["<b>④ 웹 서비스 UX/UI · 퍼블리싱</b><br/>- 입력창 · 생성 버튼<br/>- 로그인(구글 ID)<br/>- 결과화면 · SNS 공유<br/>- MYPAGE(기존 생성물 조회/삭제)"]
    Step5["<b>⑤ 출력: 영상 / 쇼핑 링크 / 이미지</b><br/>- 8초 영상<br/>- 이미지 1~2컷<br/>- 워터마크 등"]
    Step6["<b>⑥ 저장·배포(YouTube) & 운영</b><br/>- 영상 저장은 DB 대신 YouTube 중심<br/>- 운영 모니터링(회원, 삭제, 이력관리)<br/>- 초상권·개인정보 처리 정책 적용"]
    Step7["<b>⑦ BM / 유료화 / 시스템 확장</b><br/>- 무료 체험 → 유료 전환<br/>- ID별 사용 횟수 제한<br/>- 내 사진 기반 프리미엄 모델<br/>- 제휴(패션몰/브랜드)<br/>- 시스템 범위 확장(뷰티/주얼리 등)"]
    %% 연결선 및 흐름
    Step1 --> Step2
    Step2 --> Step3
    Step3 --> Step4
    Step4 --> Step5
    Step5 --> Step6
    Step6 --> Step7
    %% 클래스 적용 (핵심 단계인 3, 4번에 하이라이트 색상 적용 예시)
    class Step1,Step2,Step5,Step6,Step7 step;
    class Step3,Step4 highlight;