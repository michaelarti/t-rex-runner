## t-rex-runner

the trex runner game extracted from chrome offline err page.

see the [source](https://cs.chromium.org/chromium/src/components/neterror/resources/offline.js?q=t-rex+package:%5Echromium$&dr=C&l=7) from chromium


[go and enjoy! :smile: ](http://wayou.github.io/t-rex-runner/)

![chrome offline game cast](assets/screenshot.gif)

---

## 이 포크의 커스텀 기능 (Custom Features)

원본 크롬 오프라인 게임을 확장해 다음 기능들을 추가했습니다. 모든 변경은 [`index.js`](index.js)에 있으며, 추가 에셋 없이 기존 스프라이트와 캔버스 절차적 그리기로 구현했습니다.

### 🦖 무지개 T-Rex와 칼
- **무지개 T-Rex**: 회색 스프라이트를 흐르는 무지개 그라데이션으로 리컬러링해서 그립니다.
- **칼(sword)**: T-Rex가 칼을 듭니다. 달리거나 점프할 때는 머리 위로, 숙일 때는 앞으로 찌르는 자세로 칼이 따라 움직입니다.

### 🦔 고슴도치 장애물
- **지상 고슴도치**: 점수 100점마다 등장하는 특수 장애물. 가변 속도(`speedOffset .6`)로 수평선보다 빠르거나 느리게 움직입니다.
- **날아다니는 고슴도치**: 익룡처럼 공중을 나는 새 장애물. 속도가 빨라지면(`minSpeed 5`) 랜덤 등장하며, 가변 속도(`speedOffset .9`)로 날갯짓하며 날아옵니다.

### ❤️ 생명력(HP) 시스템
- 시작 생명력 **1**, 최대 **7**. 좌상단에 `[N] ♥♥♥` 형식으로 숫자 + 하트를 표시합니다(HI 점수와 같은 높이).
- 장애물에 부딪히면 생명력 **−1**. 피격 직후 잠시 무적 상태가 되어 T-Rex가 깜박이며 그 장애물을 통과합니다.
- 생명력이 **0**이 되면 게임 오버.

### ⚔️ 칼 공격
- **엔터(Enter)** 키로 칼을 휘두릅니다.
- 고슴도치/날아다니는 고슴도치가 **부딪치기 바로 직전(가까울 때)** 휘둘러야 명중합니다. 멀리 떨어져 있으면 빗나갑니다.
- 날아다니는 고슴도치는 **높이를 맞춰야**(점프해서) 명중합니다.
- 정확히 맞히면: 고슴도치가 **반으로 쪼개지며 사라지고**, 생명력 **+1**, 점수 **+100**(점수 위로 `+100`이 떠올라 1초 안에 사라지는 연출).

### 🎮 조작 (Controls)
| 키 | 동작 |
| --- | --- |
| `Space` / `↑` | 점프 |
| `↓` | 숙이기 |
| `Enter` | 칼 휘두르기 (게임 중) / 재시작 (게임 오버 시) |

