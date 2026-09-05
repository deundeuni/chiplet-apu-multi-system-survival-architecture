# soma-moa: 칩렛-APU 다중 시스템 생존 아키텍처 v2.6 (Final)


> **"볼트 하나가 풀려도 전체 시스템이 무너지지 않게 예비 경로가 있어야 하며, 부품 하나가 쓰러지면 옆 부품이 즉시 바통을 이어받아야 한다."**

`soma-moa`는 거대 반도체, AI 가속기, 자율주행 모빌리티, 로보틱스 생태계를 위한 **무중단 생존형 공용 오픈 아키텍처 규격**입니다. 단일 장애점(SPOF)을 원천 차단하고, L0 물리 소재부터 L3 소프트웨어 제어까지 연결되는 풀스택 자가치유 및 백혈구 면역 스캔 시스템을 제공합니다.

---

## 📂 프로젝트 파일 구조

- **[WHITEPAPER.ko.md]** : 공식 선행기술 방어 백서 전문 (Full Text)
- **[PHILOSOPHY.md]** : 창안자 원안 철학 및 현장 동기
- **[LICENSE]** : CC BY 4.0 & DPL v1.0 라이선스 명세

---

## 🏗️ 풀스택 레이어 개요

```text
┌────────────────────────────────────────────────────────────────────────┐
│ [L2-L3] 제어 소프트웨어 & 프로토콜 (Control Software & Protocols)        │
│ - OS 커널 드라이버, CXL 가상 메모리 매퍼, Raft 자가 치유 마이크로코드       │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │ (텔레메트리 & 백프레셔 신호)
┌──────────────────────────────────▼─────────────────────────────────────┐
│ [L1] 팀리더(TL) & 칩렛 연산 패브릭 (TL & Chiplet Fabric Layer)          │
│ - CPU / TL 브리지 / 연산 기공(GPGPU/NPU) / CXL 메모리 풀링               │
│ - N-확장형 메쉬 패브릭 + 갓길 3중 관제 + T-Reg 억제 + 물리 격리 회로       │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │ (초고속 신호 & 전원 버스)
┌──────────────────────────────────▼─────────────────────────────────────┐
│ [L0] 메인보드 물리 및 소재 레이어 (Baseboard Physical & Material)        │
│ - 0.1ms HW E-Stop PMIC/MOSFET, 리타이머, 독립 Safety IP 전원/클럭 영역  │
│ - [3C 연계] 차동 감속 도킹, V홈 자율 정렬, 패시브 생체모방 습윤 코팅      │
└────────────────────────────────────────────────────────────────────────┘
```

## ⚖️ 지적재산권 및 방어적 라이선스 (DPL)

본 백서는 특정 기업의 기술 사유화를 방지하고 공익적 오픈 표준을 보호하기 위해 DPL (Defensive Publication License v1.0) 및 CC BY 4.0을 적용합니다.
* Root Origin & Primary IP Owner: deundeuni (soma-moa)
* Official Domain: somamoa.ai.kr

## 출처 및 기록 (Sources & Records)

* **소마모아 생태계 저장소 및 학술 식별자 (Ecosystem Repositories & DOIs)**
  * 상위 범용 생존 아키텍처 & APU 연산 제어기 (`chiplet-apu-multi-system-survival-architecture`) — GitHub: `deundeuni / chiplet-apu-multi-system-survival-architecture` | CERN Zenodo DOI: `10.5281/zenodo.22374987` (https://doi.org/10.5281/zenodo.22374987)
  * 재난 피난 유도 & 보조 인프라 (`LAST-LIGHT`) — GitHub: `deundeuni / LAST-LIGHT` | CERN Zenodo DOI: `10.5281/zenodo.22373189` (https://doi.org/10.5281/zenodo.22373189)
  * 극지 해양 희생장갑 (`MAX-LIFE-ICE-BELT`) — GitHub: `deundeuni / MAX-LIFE-ICE-BELT` | CERN Zenodo DOI: `10.5281/zenodo.22373686` (https://doi.org/10.5281/zenodo.22373686)
  * CWP 배터리 교환 도킹 (`CWP-Battery-Swap`) — CERN Zenodo DOI: `10.5281/zenodo.22373538` (https://doi.org/10.5281/zenodo.22373538)
  * CWP 전자기 클램핑 (`CWP-Clamping-Battery-Swap-System`) — CERN Zenodo DOI: `10.5281/zenodo.22373722` (https://doi.org/10.5281/zenodo.22373722)
  * CWP 롤링 셀프얼라인 (`CWP-Rolling-Self-Align-Battery-Swap-System`) — CERN Zenodo DOI: `10.5281/zenodo.22373704` (https://doi.org/10.5281/zenodo.22373704)
  * 최상위 거점 관문 및 메인 저장소 (`soma-moa`) — GitHub: `deundeuni / soma-moa` | 관문 도메인: `somamoa.ai.kr`

* **국제 기술 표준 및 참조 규격 (International Technical Standards)**
  * ISO 7010 / ISO 16069 — Graphical symbols, Safety colours and Safety Way Guidance Systems (SWGS)
  * Bluetooth SIG Specification — Auracast / LE Audio Broadcast Specifications
  * IEEE 802.15.4z / UWB Standard — Ultra-Wideband Positioning and Ranging Standards
  * ISO 8501 — Surface Cleanliness and Preparation Standards for Steel Substrates
  * IMO AFS Convention & EU MSFD — International Convention on the Control of Harmful Anti-fouling Systems & Marine Strategy Framework Directive
  * Classification Society Ice Class Rules — 한국선급(KR), DNV, ABS 극지 운항 아이스벨트 구조 규격

* **공지기술 원용 및 학술적 배경 (Public Domain Prior Art & Physics)**
  * Béla Barényi (1951) — Automotive Passive Safety Architecture (Crumple Zone & Sacrificial Structural Sacrifice)
  * Public Domain Kinematics & Clamping — N/(N+1) Differential Reduction, Electro-Permanent Magnet (EPM) Control Logic

* **법적 근거 및 선사용권 규정 (Legal Statutes & Precedents)**
  * 대한민국 특허법 제103조 — 선사용에 의한 통상실시권
  * 미국 특허법 35 U.S.C. §273 — Defense to Infringement Based on Prior Commercial Use
  * 대한민국 「소방시설 설치 및 관리에 관한 법률」 및 「건축법」 — 법정 유도 설비 및 비상 전력 기준

* **선행기술 증명 고지 (Defensive Prior Art Statement):** 본 명세서에 개시된 기술적 사상, 도안 및 참조 표준 연계 구조는 GitHub 불변 커밋 해시(Commit Hash) 및 CERN Zenodo / DataCite 글로벌 학술 레지스트리에 타임스탬프 기록이 등재되어 있습니다. 이는 제3자의 사적 독점 특허화 위험을 완화하고, 전 세계 특허 심사 시 공공 영역의 선행기술(Prior Art)로 참조되어 신규성 및 진보성 논박 근거로 활용 가능하도록 돕는 것을 지향합니다.

* **비의도적 생략 및 예시적 미한정 고지 (Non-Intentional Omission & Non-Exhaustive Disclaimer):** 본 명세서에 인용되거나 열거된 기술 표준, 공지 원리, 법령 및 관련 저장소 목록은 이해를 돕기 위한 예시적 서술이며 전면적·고착적 한정을 의미하지 않습니다. 작성자의 주관적 한계나 인지적 착오로 인해 특정 세부 규격, 관련 산업 표준, 후속 개정안 또는 균등 선행기술의 명시가 누락되거나 누적 생략되었을 수 있으나, 이는 의도적인 은폐나 배척이 아닙니다. 개시된 상위 기술 사상과 연결되는 모든 파생 표준, 개정 규격, 균등 기구 및 공지기술 조합은 본 방어적 공개 백서의 선행기술 포괄 범주에 포함된 것으로 간주합니다.

