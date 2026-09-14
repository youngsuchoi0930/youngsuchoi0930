<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:161826,50:5d5294,100:9184d9&height=190&section=header&text=%EC%B5%9C%EC%98%81%EC%88%98&fontColor=ffffff&fontSize=54&fontAlignY=38&desc=AI%20Application%20Developer&descAlignY=58&descSize=17" alt="최영수 — AI Application Developer" />
</p>

## 현장의 요구를 AI 서비스로 잇는 개발자, 최영수입니다.

2년 7개월의 기술영업에서 고객 요구 분석부터 사양 제안, 납품과 사후관리까지 맡았습니다. 고객의 말을 기술 요구로 정리하던 경험을 바탕으로, 지금은 **AI·백엔드·화면·배포를 연결해 사용자의 문제를 해결합니다.**

상담 응답이 늦을 때는 실제 대화 간격으로 연결 지연을 측정했고, 손 추적 화면이 느릴 때는 그리기와 서버 전송을 분리했습니다. 제가 맡은 일과 그 과정에서 내린 선택을 아래에 담았습니다.

**[포트폴리오 · 작업 과정](https://youngsu-resume.vercel.app/)** · **[이력서 PDF](https://youngsu-resume.vercel.app/choi-youngsu-resume.pdf?v=20260914-story)** · [이메일](mailto:y1692543@gmail.com)

### 대표 프로젝트

| 프로젝트 | 해결하려는 문제 | 내가 맡은 일 |
|---|---|---|
| **[ManualGo](https://github.com/youngsuchoi0930/manualgo)** · 개인 | 기기를 다루는 중에도 음성으로 매뉴얼의 근거 페이지를 찾기 | 문서 처리·검색·음성 응답·출처 UI·평가 전 과정 |
| **[Jobiverse](https://github.com/youngsuchoi0930/job_simulator)** · 6인 팀 | 직무 상담을 실제 업무 체험으로 이어가기 | AI 코치·NPC 프롬프트, 미니게임 구현, RAG 지식베이스, 추천 보정·운영 |
| **[야구 볼래](https://github.com/youngsuchoi0930/KBO_coach)** · 6인 팀 | 야구 입문자가 대화와 캐릭터를 통해 규칙·문화를 익히기 | 프론트엔드·UI/UX, 3D 모델 최적화·구단 스킨·모션 |
| **[피어나](https://github.com/youngsuchoi0930/KSL-Project)** · 4인 팀 | 주민센터에서 수어와 음성으로 의사소통하기 | 키오스크·상담원 UI, 지점별 DB 분리, 배포·실시간 표시 최적화 |

### 문제를 풀며 남긴 선택들

#### ManualGo · 정답처럼 보이는 숫자를 의심하는 일

문서를 보고 만든 평가 질문이 매뉴얼의 표현을 그대로 쓰고 있었습니다. 정답은 유지하고 질문만 구어체로 바꾼 200문항에서 제품 선택 경로의 R@1이 **0.815 → 0.495**로 떨어졌습니다. 평가가 사용자의 말투를 놓치고 있었습니다.

구어체 평가를 640문항으로 넓히고, 구성 선택과 검증에 각각 320문항을 사용했습니다. 제품 선택 경로는 임베딩 검색과 리랭커를 채택하고 전체 검색은 기존 융합을 유지했습니다. 최종 홀드아웃의 제품 선택 R@5는 **0.878**입니다. 재작성한 평가 질문 기준이며 실제 사용자 이용 데이터와는 구분합니다.

[평가 설계·실험표 (§10·§11)](https://github.com/youngsuchoi0930/manualgo/blob/main/README.md) · [작업 과정](https://youngsu-resume.vercel.app/#manualgo-process)

#### Jobiverse · 대화가 이어지려면, 기다림부터 줄여야 했습니다

3초 간격의 테스트는 빨랐지만, 실제 상담처럼 20~40초 뒤에 질문하면 느려졌습니다. HTTP 연결 유지 시간이 5초여서 매 턴 연결을 다시 맺는 것이 원인이었습니다. 유지 시간을 조정하고 운영 VM에서 21턴을 재측정해 첫 응답 중앙값 **2,591 → 1,550ms**를 확인했습니다.

상담 프롬프트에서는 요청문까지 질문으로 세고, 사용자 표현을 되짚되 같은 인사말을 반복하지 않도록 수정했습니다. 이 과정에서 측정 간격과 평가 기준도 구현만큼 중요하다는 것을 배웠습니다.

[본인 연결 지연 수정](https://github.com/youngsuchoi0930/job_simulator/commit/9eb278967bed2d2328b6fe49a94b0c8f0d017bb8) · [본인 프롬프트 수정](https://github.com/youngsuchoi0930/job_simulator/commit/d26713a0802cb0333d5bcbdb479be9e9b720d1a6) · [측정 조건·과정](https://youngsu-resume.vercel.app/#jobiverse-process)

#### 야구 볼래 · 캐릭터의 표정은 살리고, 무게는 덜어내는 일

새 3D 모델은 725MB였습니다. 구단별 스킨과 움직임을 유지하기 위해 재질·리깅·애니메이션을 보존하면서 Draco·WebP를 적용해 **56.7MB**로 줄였습니다. 모션 전환의 깜빡임은 크로스페이드로, 배트 때문에 치우친 화면 배치는 몸통 기준 중심 계산으로 보정했습니다.

파일을 줄일 때도 사용자가 보게 될 스킨과 움직임을 함께 확인했습니다. 용량 감소와 실제 로딩 속도 개선은 별도로 검증해야 한다는 점도 남겨 두었습니다.

[본인 모델·스킨·모션 작업](https://github.com/youngsuchoi0930/KBO_coach/commit/28df586584b5c8f86075173c2b038766a0b1bc8a) · [작업 과정](https://youngsu-resume.vercel.app/#yagu-process)

#### 피어나 · 손을 따라오지 못하던 화면을 고쳤습니다

카메라는 60fps인데 손의 윤곽은 6fps였습니다. 서버 응답을 기다린 뒤 그리는 구조를 확인하고 MediaPipe 검출을 브라우저로 옮겼습니다. 배포 환경에 남은 지연은 **로컬 그리기와 서버 전송을 분리**해 해결했고, 갱신율은 **30~40fps**로 회복됐습니다.

계산 위치를 바꾼 뒤에도 무엇을 기다리는지 확인해야 했습니다. 제 담당은 화면·DB·배포·실시간 표시 최적화이며, 수어 모델 학습은 팀원이 맡았습니다.

[본인 작성 진단·개선 문서](https://github.com/youngsuchoi0930/KSL-Project/blob/main/docs/랜드마크_지연개선_2026-06-26.md) · [그리기·전송 분리 커밋](https://github.com/youngsuchoi0930/KSL-Project/commit/43685675b63adf22dae7f7fc0677e61ec15908fb) · [작업 과정](https://youngsu-resume.vercel.app/#pierna-process)

### 교육과 수상

**이스트소프트 KDT AI 휴먼과정 수료 · 2026.03–07**

| 과정 내 평가 | 프로젝트 | 결과 | 소속 팀 |
|---|---|---|---|
| 최종 프로젝트 | Jobiverse | **대상 · 6개 팀 중 1위** | 6인 |
| 2차 프로젝트 | 야구 볼래 | **대상 · 6개 팀 중 1위** | 6인 |

두 평가의 기준은 **기획성·창의성·엔지니어의 가치**이며, 수상은 팀 전체의 성과입니다.

### 사용하는 기술

| 영역 | 프로젝트에서 사용한 기술 |
|---|---|
| AI·검색·음성 | LLM, RAG, pgvector, ONNX, PyTorch, MediaPipe, Azure Speech |
| 백엔드 | Python, FastAPI, Flask, REST, WebSocket·SSE |
| 프론트엔드·모바일 | TypeScript, React, Capacitor, three.js, WebRTC |
| 데이터·배포 | PostgreSQL, SQLite, MongoDB, Redis, Docker, GCP, Vercel, GitHub Actions |

<details>
<summary>학습과 탐색 기록</summary>

- PyTorch로 Transformer의 어텐션 구조 직접 구현
- [재활용 분류 앱](https://github.com/youngsuchoi0930/recycle_app) — MobileNetV2·TFLite·Flutter 온디바이스 분류
- 한국어 TTS·Voice Cloning — XTTS-v2·OpenVoice V2·MeloTTS 비교
- 음성 분류 — MFCC·Mel-spectrogram 기반 오디오 전처리

</details>

<details>
<summary>GitHub 활동</summary>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/youngsuchoi0930/youngsuchoi0930/output/github-snake-dark.svg" />
  <img alt="GitHub 기여 활동 시각화" src="https://raw.githubusercontent.com/youngsuchoi0930/youngsuchoi0930/output/github-snake.svg" />
</picture>

</details>

---

[포트폴리오](https://youngsu-resume.vercel.app/) · [이력서 PDF](https://youngsu-resume.vercel.app/choi-youngsu-resume.pdf?v=20260914-story) · [LinkedIn](https://www.linkedin.com/in/youngsuchoi0930) · [y1692543@gmail.com](mailto:y1692543@gmail.com) · Seoul
