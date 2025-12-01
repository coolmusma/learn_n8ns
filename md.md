flowchart TD
    %% 스타일 정의
    classDef phase fill:#f0f4f8,stroke:#333,stroke-width:2px;
    classDef item fill:#ffffff,stroke:#666,stroke-width:1px,rx:5,ry:5;
    classDef option fill:#fffbe6,stroke:#d4b106,stroke-width:1px,stroke-dasharray: 5 5;

    %% 1단계: 기획 설계
    subgraph Step1 [<b>① 기획 설계</b>]
        direction TB
        S1_1(서비스 목적 정의) --> S1_2(유저 시나리오 / 페르소나)
        S1_2 --> S1_3(정책 / BM 설계)
        S1_3 --> S1_4(기능 정의 및 화면 흐름 설계)
    end

    %% 2단계: 데이터 수집
    subgraph Step2 [<b>② 데이터 수집 구조 설계</b>]
        direction TB
        S2_1(소스 선정) --> S2_2("스크래핑 방식 (병합/루프)")
        S2_2 --> S2_3("데이터 포맷 정리 (PDF/XML → Binary)")
    end

    %% 3단계: n8n 자동화
    subgraph Step3 [<b>③ n8n 자동화 파이프라인</b>]
        direction TB
        S3_1(스크래핑 → 이미지 생성) --> S3_2(이미지 → 영상 생성)
        S3_2 --> S3_3(영상 → 폴더 저장)
        S3_3 -.-> S3_4(옵션: 유튜브 자동 업로드):::option
    end

    %% 4단계: 웹 서비스
    subgraph Step4 [<b>④ 웹 서비스 UX/UI</b>]
        direction TB
        S4_Login(로그인: 구글 ID) --> S4_Input(입력창 · 생성 버튼)
        S4_Input --> S4_Result(결과화면 · SNS 공유)
        S4_Result --- S4_My(MYPAGE: 조회/삭제)
    end

    %% 5단계: 출력물
    subgraph Step5 [<b>⑤ 출력 결과물</b>]
        direction TB
        S5_1(8초 영상) --- S5_2(이미지 1~2컷)
        S5_1 & S5_2 --- S5_3(워터마크)
    end

    %% 6단계: 운영/배포
    subgraph Step6 [<b>⑥ 저장·배포 & 운영</b>]
        direction TB
        S6_1(영상 저장: YouTube 중심)
        S6_2(운영 모니터링: 회원/이력)
        S6_3(초상권 · 개인정보 정책)
        S6_1 --- S6_2 --- S6_3
    end

    %% 7단계: BM 확장
    subgraph Step7 [<b>⑦ BM / 유료화 / 확장</b>]
        direction TB
        S7_1(무료 체험 → 유료 전환) --> S7_2(ID별 사용 횟수 제한)
        S7_2 --> S7_3(내 사진 기반 프리미엄)
        S7_3 --- S7_4(제휴: 패션몰/브랜드)
        S7_4 --- S7_5(확장: 뷰티/주얼리 등)
    end

    %% 전체 단계 연결
    Step1 ==> Step2
    Step2 ==> Step3
    Step3 ==> Step4
    Step4 ==> Step5
    Step5 ==> Step6
    Step6 -.-> Step7

    %% 클래스 적용
    class Step1,Step2,Step3,Step4,Step5,Step6,Step7 phase;
    class S1_1,S1_2,S1_3,S1_4,S2_1,S2_2,S2_3,S3_1,S3_2,S3_3,S4_Login,S4_Input,S4_Result,S4_My,S5_1,S5_2,S5_3,S6_1,S6_2,S6_3,S7_1,S7_2,S7_3,S7_4,S7_5 item;