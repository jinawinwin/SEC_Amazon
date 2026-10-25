# Amazon SEC Financial Dashboard

[![🔗 대시보드 바로가기](https://img.shields.io/badge/%F0%9F%94%97%20%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%20%EB%B0%94%EB%A1%9C%EA%B0%80%EA%B8%B0-Visit%20Dashboard-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)](https://jinawinwin.github.io/SEC_Amazon/)

Amazon.com, Inc. (CIK 1018724)의 SEC EDGAR XBRL 공시를 모아 매출·수익성·재무상태·현금흐름을 살펴보는 대시보드입니다.

## 대시보드

[🔗 Amazon 재무 대시보드](https://jinawinwin.github.io/SEC_Amazon/)

상단 figures는 분기별 매출·순이익 및 현금흐름을 보여주고, 연간·반기·분기 표에서 공시 재무 수치를 확인할 수 있습니다. 우측 PDF 저장은 브라우저 인쇄 기능을 사용하고, Excel 다운로드는 기간별 표를 내려받습니다.

## 분석 지표

매출, 매출총이익, 영업이익, 순이익, 희석/기본 EPS, 자산, 부채, 현금, 영업현금흐름, 자본적 지출, 잉여현금흐름, 매출 성장률, 마진, 현금전환율, 부채/자산 및 유동비율을 제공합니다. 금액은 USD millions, 주당 수치는 USD입니다. 반기 공시 및 분기 합산을 활용하며 4분기와 누락 분기는 연간/누계 값 차감으로 산출합니다. XBRL 태그/정정공시로 과거 수치가 달라질 수 있습니다.

## Global peer firms

| 기업 | 티커 | 비교 관점 |
|---|---|---|
| Walmart Inc. | WMT | 글로벌 대형 종합 소매 및 전자상거래 |
| Alibaba Group Holding Ltd. | BABA | 글로벌 온라인 마켓플레이스 및 클라우드 |
| eBay Inc. | EBAY | 글로벌 온라인 마켓플레이스 |
| Shopify Inc. | SHOP | 전자상거래 인프라 및 판매자 플랫폼 |
| MercadoLibre, Inc. | MELI | 중남미 전자상거래 및 핀테크 플랫폼 |
| Target Corporation | TGT | 대형 소매 및 디지털 커머스 |

비교 대상은 사업 모델 및 온라인 유통 노출도를 바탕으로 선정했습니다. Amazon과 peer의 사업 구성, 규모, 회계연도 및 회계정책은 서로 달라 직접 비교에 한계가 있습니다. 대시보드는 Amazon SEC 수치만 표시합니다.

## SEC 원자료 및 자동 갱신

SEC [Company Facts API](https://data.sec.gov/api/xbrl/companyfacts/CIK0001018724.json)와 [EDGAR 제출 내역](https://www.sec.gov/edgar/browse/?CIK=1018724&owner=exclude)을 원천으로 사용합니다. `scripts/update_data.py`가 원자료를 `data/companyfacts.json`, 정제 수치를 `data/financials.json`에 저장합니다. GitHub Actions가 매월 5일 00:00 UTC (한국시간 09:00)에 데이터를 갱신하고 GitHub Pages를 배포합니다. 최초 실행 전에 Settings → Secrets and variables → Actions에서 모니터링 가능한 이메일을 `SEC_CONTACT_EMAIL` secret으로 등록하세요. 이후 Actions에서 `Update Amazon SEC dashboard` workflow를 수동 실행하면 첫 수집 및 배포를 시작할 수 있습니다.
