## 💻 Full-Custom CMOS VLSI Design Project

### 🌟 프로젝트 개요 (Project Overview)

본 프로젝트는 EDA (Electronic Design Automation) 툴을 활용하여 Full-Custom 방식으로 기본적인 디지털 회로 구성 요소(셀 라이브러리)와 조합 논리 회로인 3x8 Decoder를 설계하고 검증하는 것을 목표로 했습니다.

설계 방식: CMOS Full-Custom Design
사용 툴: Cadence Virtuoso Layout Suite, DRC/LVS Tool
핵심 목표: 트랜지스터 수준에서 레이아웃을 직접 설계하고, DRC 및 LVS를 통과시켜 회로의 물리적 구현 능력 검증.

---

### 🧱 Full-Custom 셀 라이브러리 설계 및 검증

프로젝트의 기초가 되는 CMOS 논리 게이트와 순차 논리 회로를 Master-Slave D-F/F까지 직접 설계하고 레이아웃을 최적화했습니다.

| Cell Name | 기능 | 면적 (Width X Height) | 결과 면적 | DRC 상태 | LVS 상태 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 2-input NAND | 논리 NAND 게이트 | (1.36 X 8.78) | 1.94  |Pass (No errors) | Match  |
|2-input NOR | 논리 NOR 게이트 | (1.36 X 8.78) |11.94  | Pass (No errors)| Match  |
|3-input NAND] | 논리 NAND 게이트 | (1.78 X 8.78) | 15.62 | Pass (No errors)  | Match  |
|3-input NOR | 논리 NOR 게이트 | (1.78 X 8.78) |15.62  |Pass (No errors)| Match |
|Master-Slave D-F/F | 순차 논리 회로 | (13.6 X 8.78) | 119.4  |Pass (No errors)  | Match  |

#### 1. 레이아웃 설계 (Layout Design)
각 셀은 P-Type 트랜지스터(PMOS)와 N-Type 트랜지스터(NMOS)를 이용하여 Schematic을 구현한 후, 레이아웃 단계에서 Full-Custom 방식으로 트랜지스터와 배선(Metal Layers)을 직접 배치했습니다.

#### 2. 물리적 검증 (Physical Verification)
DRC (Design Rule Check): 모든 셀에서 제조 공정 규칙 위반이 없는 `No DRC errors found` 결과를 확보하여, 물리적 구현의 안정성을 확인했습니다.
LVS (Layout Versus Schematic): 모든 셀에서 Schematic과 Layout 간의 연결(Net), 소자(Device), 핀(Pin), 파라미터(Parameter)가 일치하는 `Schematic and Layout Match` 결과를 얻어, 논리적 설계와 물리적 구현 간의 완벽한 일치성을 검증했습니다.

---

### 🥇 핵심 프로젝트: 3x8 Decoder 설계

앞서 설계한 셀 라이브러리를 기반으로, 3개의 입력(A, B, C)과 8개의 출력(D0~D7)을 갖는 3x8 Decoder 조합 논리 회로를 Full-Custom으로 통합 설계했습니다.

#### 1. 회로 구조 (Schematic)
  3x8 디코더는 3개의 입력에 대한 8가지 조합을 각각 활성화하는 8개의 출력으로 구성됩니다.
  디코더는 인버터(Inverter) 및 3-input NOR 게이트를 조합하여 구현되었습니다. 

#### 2. 레이아웃 결과 (Layout)
셀 이름: `3X8_Decoder` 
면적 (Width X Height): (17.06 X 8.78) 
결과 면적: 149.78 

#### 3. 최종 검증 및 시뮬레이션

| 검증 항목 | 결과 | 상세 내용 |
| :--- | :--- | :--- |
| DRC | Pass | `No DRC errors found` 확보  |
| LVS | Match | `Schematic and Layout Match` 확보 |
| Transient Simulation | 동작 확인 | 모든 입력 조합(X, Y, Z)에 대해 8개 출력(D0~D7)이 논리적으로 올바르게 활성화되는 것을 Spectre 시뮬레이션으로 확인했습니다.  |


---

### 🔑 주요 성과 (Key Achievements)

EDA 툴 숙련도: Cadence Virtuoso 환경에서 Schematic Entry, Full-Custom Layout, 그리고 DRC/LVS/Simulation에 이르는 IC 설계의 전 과정을 독자적으로 수행하여 EDA 툴 사용 능력을 극대화했습니다.
물리적 설계 이해 마스크 레이어, 디자인 룰(Design Rule)을 준수하며 면적 효율성을 고려한 레이아웃을 직접 설계함으로써, 디지털 회로의 물리적 구현 특성에 대한 깊이 있는 이해를 확보했습니다.
회로 무결성 검증 DRC 및 LVS를 완벽하게 통과시켜 설계된 회로의 논리적/물리적 무결성(Integrity)을 검증했습니다.
