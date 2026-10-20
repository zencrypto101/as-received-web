# The As-Received Web — 데이터셋 릴리스 2026-10-18

동결 시각: 2026-10-18T12:37:02+0800 · 표본 20곳(수신 계층 19곳 측정, 행동 계층 19곳 측정) · 편의 표본

## 파일

| 파일 | 내용 |
|---|---|
| `receive_layer_2026-10-18.csv` | 사이트별 수신 계층 판정(엑셀에서 바로 열림) |
| `action_layer_2026-10-18.csv` | 사이트별 행동 계층 판정 |
| `dataset_2026-10-18.json` | 위 두 계층 + 집계 + 메타(스키마 1) |
| `raw/` | 원시 실행 JSON·누적 원장 원본 |
| `sha256.txt` | 모든 파일의 해시(동결 증명) |

## 발행 숫자 (동결 파일에서 직접 계산)

**수신 계층**

| 지표 | 값 |
|---|---|
| measured | 19/20 |
| llms_txt_pass | 9/19 |
| md_negotiation_pass | 6/19 |
| md_serving_for_vary_denominator | 6 |
| vary_asym | 2/6 |
| soft200_trap | 2/19 |
| robots_blocking_any_ai_agent | 4/19 |
| payload_ratio_median | 87x |
| payload_ratio_max | 690x |

**행동 계층**

| 지표 | 값 |
|---|---|
| measured | 19/20 |
| server_form_zero | 11/19 |
| product_jsonld_zero | 19/19 |
| task_links_zero | 5/19 |
| agent_endpoints_zero | 15/19 |

## 분류별 (수신 계층, 마크다운 협상 제공)

- agency: 0/3
- commerce-global: 0/5
- commerce-sg: 1/3
- docs: 4/4
- media: 0/2
- saas: 1/2

## 방법 (그대로 인용 가능)
- 요청은 우리가 직접 보낸다. API 0 · 외부 패키지 0 · 서버 0 (Python 표준 라이브러리만).
- **정직 UA 1종**: `AsReceivedAudit/1.0 (site-owner-requested verification)`. **UA 위장 없음.**
- **robots.txt 준수**: 우리 UA(또는 `*`)가 금지한 경로는 요청하지 않고 "제외"로 기록한다.
- 도메인 간 병렬 5, 도메인 내부는 순차. 요청 1건당 15초 하드 상한(소켓 레벨).
- 수신 계층 신호: llms.txt · 마크다운 협상(`Accept: text/markdown`) · `.md` 접미사 · `Vary` · 페이로드 배율 · robots 선언 정책.
- 표본은 **편의 표본(무작위 아님)**. 구성은 데이터셋의 `category` 열에 그대로 있다.

## 이 데이터가 주장하지 않는 것
- **에이전트가 방문·시도·구매했는가**: 측정하지 않았다. 로그가 필요하다. **주장하지 않는다.**
- **절대 점수·순위**: 발행하지 않는다. 항목별 O/X(판정 클래스)와 배율만 기록한다.
- **AI 에이전트 UA 차등**: UA를 위장하지 않으므로 실측하지 않았다. robots.txt **선언 정책**만 기록했다.
- **JS 렌더 이후 화면**: 미측정. 헤드리스 브라우저를 쓰지 않았다. 모든 수치는 **서버 응답 기준**이다.
- **k=1**: 단일 시점 1회 측정이다. 시계열 변화는 같은 방법의 재실행 diff로만 주장할 수 있다.
- **상품 상세 페이지(PDP)**: 미측정. 이 릴리스는 각 사이트의 **진입 URL**만 본다.

## 이 릴리스에 포함되지 않은 것
- `nav_links`(서버 HTML의 이동 가능 링크 수) 신호는 이 동결 **이후** 도구에 추가됐다. 릴리스 v2에서 포함한다.
- PDP 측정, 시계열(2번째 시점) — 다음 릴리스.
