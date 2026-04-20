# MEMORY.md — skills_claude 프로젝트 핵심 정보

## 프로젝트 개요
주식·암호화폐 자동 모니터링 및 트레이딩 시그널 생성 시스템.
가격 조건 충족 시 Telegram으로 알림을 전송한다.

---

## 파일 구조
```
skills_claude/
├── MEMORY.md                    # 이 파일
├── README.md                    # 프로젝트 제목만 있음
├── Get_trading_signals.ipynb    # 통합 시그널 모니터링
└── Sell_BITU.ipynb              # BITU 전용 리스크 관리
```

---

## 노트북별 핵심 내용

### Get_trading_signals.ipynb
- **역할**: 여러 종목의 매수·매도 시그널 생성 및 5분 주기 모니터링
- **매도 조건**
  - ARM ≤ $155
  - BITU 낙폭 ≤ -20% → 즉시 청산
  - 우리기술: 즉시 매도 (상장폐지 대응)
- **매수 조건**
  - 삼성전자 ≤ 82,000원
  - 한화에어로스페이스 ≤ 270,000원
  - 고려아연 ≤ 500,000원
- **모니터링 주기**: 5분

### Sell_BITU.ipynb
- **역할**: BITU 3단계 분할 매도 + 손절 전략
- **매도 단계**
  - 1차 분할 매도 (30%): $15.00
  - 2차 분할 매도 (40%): $16.00
  - 손절: $13.90
- **중복 알림 방지**: `alert_sent_*` 플래그로 재전송 차단
- **모니터링 주기**: 1분

---

## 기술 스택
| 항목 | 내용 |
|------|------|
| 언어 | Python 3.12 |
| 실행 환경 | Jupyter / Google Colab |
| 시세 데이터 | yfinance 0.2.66 |
| 데이터 처리 | pandas 2.2.2, numpy 2.0.2 |
| HTTP | requests 2.32.4 |
| 알림 | Telegram Bot API |
| 시간대 | pytz 2025.2 |

---

## Telegram 설정
- **Bot Token**: 노트북 내 하드코딩 (`7796181604:AAG...`)
- **Chat ID**: `8528061505`
- 보안 개선 필요: 환경변수 또는 secrets 관리 권장

---

## 주요 참고 사항
- 한국 주식 데이터는 yfinance 오류 발생 시 `except: continue`로 무시됨
- 우리기술은 상장폐지로 데이터 조회 불가 상태
- 일부 기능은 하드코딩 예시값(`BITU_drawdown = -0.21`) 사용 중 → 실제 연동 필요
- 두 노트북에 유사 모니터링 코드가 중복 존재 (개발 진행 중)

---

## Git 정보
- **원격 저장소**: `bomgom02-netizen/skills_claude`
- **개발 브랜치**: `claude/create-memory-file-KKQr4`
