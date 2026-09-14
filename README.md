<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:161826,50:5d5294,100:9184d9&height=190&section=header&text=%EC%B5%9C%EC%98%81%EC%88%98&fontColor=ffffff&fontSize=54&fontAlignY=38&desc=AI%20Application%20Developer&descAlignY=58&descSize=17" alt="최영수 — AI Application Developer" />
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3000&pause=800&color=9184D9&center=true&vCenter=true&width=750&lines=AI+Application+Developer;LLM+%7C+RAG+%7C+AI+Service;KDT+Team+Project+Grand+Prize+x2;Backend+to+Frontend%2C+Mobile+to+Deploy" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://youngsu-resume.vercel.app">
    <img src="https://img.shields.io/badge/웹_이력서_보러가기-9184d9?style=for-the-badge&labelColor=161826" />
  </a>
  &nbsp;
  <a href="https://youngsu-resume.vercel.app/choi-youngsu-resume.pdf?v=20260914-story">
    <img src="https://img.shields.io/badge/이력서_PDF_다운로드-5d5294?style=for-the-badge&labelColor=161826" />
  </a>
</p>

---

### 🚀 About Me

- 🎓 **이스트소프트 KDT AI 휴먼과정** 수료 (2026.03 – 07) · 과정 내 프로젝트 **대상 2회 · 각각 6개 팀 중 1위**
- 🤝 **2년 7개월의 기술영업 경험** — 고객 요구 분석·사양 제안·납품·사후관리 경험을 서비스 개발로 연결합니다
- 🧠 RAG와 LLM으로 **실제 동작하는 AI 서비스**를 만듭니다
- 🔬 Recall@k · MRR · LLM-as-judge 같은 지표로 성능을 측정하고, 실패 원인을 분석해 다시 측정합니다
- 🔗 FastAPI 백엔드부터 React 프론트엔드, Capacitor 모바일, GCP·Docker 배포까지 직접 연결합니다

> 🎯 *현장의 요구를 이해하고, AI 서비스의 구현과 배포까지 연결합니다.*

---

### 💡 Featured Projects

| 프로젝트 | 한 줄 소개 | 담당 | 핵심 기술 |
|---|---|---|---|
| 🎙️ **[ManualGo](https://github.com/youngsuchoi0930/manualgo)** | 질문을 말하면 근거 페이지와 함께 답하는 가전 매뉴얼 음성 도우미 | 개인 · 설계부터 평가까지 | `FastAPI` `Hybrid RAG` `ONNX` `Azure Speech` |
| 🧑‍💼 **[Jobiverse](https://github.com/youngsuchoi0930/job_simulator)** 🏆 KDT 최종 프로젝트 **대상** | 실시간 AI 아바타 직무 상담 + 2D 직무 체험 시뮬레이터 | AI 코치·NPC 프롬프트 · 미니게임 구현 · RAG·운영 | `FastAPI` `pgvector` `React 19` `Gemini` |
| ⚾ **[야구 볼래](https://github.com/youngsuchoi0930/KBO_coach)** 🏆 KDT 2차 프로젝트 **대상** | 팀별 페르소나 챗봇으로 배우는 KBO 입문 크로스플랫폼 앱 (웹·Android·iOS) | 프론트엔드 · 3D 캐릭터 · UI/UX 디자인 | `React 19` `Capacitor` `three.js` |
| 🤟 **[피어나](https://github.com/youngsuchoi0930/KSL-Project)** | 주민센터 창구용 수어 양방향 통역 AI 어시스턴트 | FE · DB · 배포 · 실시간 표시 최적화 | `React` `MediaPipe` `WebRTC` `GCP` |

> 🏆 **수상 범위:** 이스트소프트 KDT 과정 내 최종 프로젝트(Jobiverse)·2차 프로젝트(야구 볼래)에서 각각 **6개 팀 중 1위**를 받았습니다. 각 **6인 팀**으로 참여했으며, 평가 기준은 **기획성·창의성·엔지니어의 가치**입니다. 수상은 팀 전체의 성과입니다.

<details>
<summary>🔎 프로젝트에서 내가 해결한 문제와 배운 점</summary>

#### 🎙️ ManualGo — 정답처럼 보이는 숫자를 의심하는 일

문서 표현을 그대로 쓰던 평가 질문을 구어체로 바꾸자, 같은 정답의 200문항에서 제품 선택 R@1이 **0.815 → 0.495**로 떨어졌습니다. 이후 640문항을 튜닝·검증 각 320개로 분리하고, 제품 선택 여부에 따라 검색 구성을 다르게 적용했습니다.

**남긴 기준:** 점수와 함께 평가 질문이 사용자의 말을 닮았는지 확인합니다. 최종 제품 선택 R@5 **0.878**은 재작성된 구어체 질문의 홀드아웃 320문항 기준이며, 실제 사용자 이용 데이터는 아닙니다.

[📄 평가 설계·실험표 (§10·§11)](https://github.com/youngsuchoi0930/manualgo/blob/main/README.md) · [작업 과정 ↗](https://youngsu-resume.vercel.app/#manualgo-process)

#### 🧑‍💼 Jobiverse — 대화가 이어지려면, 기다림부터 줄여야 했습니다

실제 상담처럼 20~40초 간격으로 요청하니 매 턴 HTTP 연결이 다시 맺어지고 있었습니다. 연결 유지 시간을 조정하고 운영 VM에서 21턴을 재측정해 첫 응답 중앙값 **2,591 → 1,550ms**를 확인했습니다. 코치 프롬프트의 질문·반복 인사 규칙도 평가셋과 함께 다듬었습니다.

**남긴 기준:** 사용자가 읽고 생각하는 시간까지 측정 조건에 포함합니다. 팀 서비스의 Faithfulness **0.967**은 근거 주입 35건 기준이며, 전체 40건은 **0.846**입니다.

[🛠️ 본인 연결 지연 수정](https://github.com/youngsuchoi0930/job_simulator/commit/9eb278967bed2d2328b6fe49a94b0c8f0d017bb8) · [프롬프트 수정](https://github.com/youngsuchoi0930/job_simulator/commit/d26713a0802cb0333d5bcbdb479be9e9b720d1a6) · [작업 과정 ↗](https://youngsu-resume.vercel.app/#jobiverse-process)

#### ⚾ 야구 볼래 — 캐릭터의 표정은 살리고, 무게는 덜어내는 일

새 모델의 재질·리깅·애니메이션을 보존하면서 Draco·WebP를 적용해 **725 → 56.7MB**로 줄였습니다. 10개 구단 스킨과 모션을 구현하고, 모션 전환의 깜빡임과 배트 때문에 치우친 화면 배치를 보정했습니다.

**남긴 기준:** 최적화할 때는 유지해야 할 스킨과 움직임부터 정합니다. 파일 용량 감소를 실제 로딩 속도 개선율로 대신 표현하지 않습니다.

[🛠️ 본인 모델·스킨·모션 작업](https://github.com/youngsuchoi0930/KBO_coach/commit/28df586584b5c8f86075173c2b038766a0b1bc8a) · [작업 과정 ↗](https://youngsu-resume.vercel.app/#yagu-process)

#### 🤟 피어나 — 손을 따라오지 못하던 화면을 고쳤습니다

카메라는 60fps인데 손의 윤곽은 6fps였습니다. 검출을 브라우저로 옮긴 뒤에도 배포 환경에 지연이 남아, **로컬 그리기와 서버 전송을 분리**했습니다. 배포 환경의 갱신율은 **30~40fps**로 회복됐습니다.

**남긴 기준:** 계산 위치뿐 아니라 화면이 무엇을 기다리는지 확인합니다. 제 담당은 화면·DB·배포·실시간 표시 최적화이며, Top-1 **97.53%**는 팀원이 학습한 모델의 미학습 전문 시연자 평가 결과입니다.

[📄 본인 작성 진단·개선 문서](https://github.com/youngsuchoi0930/KSL-Project/blob/main/docs/랜드마크_지연개선_2026-06-26.md) · [분리 구현 커밋](https://github.com/youngsuchoi0930/KSL-Project/commit/43685675b63adf22dae7f7fc0677e61ec15908fb) · [작업 과정 ↗](https://youngsu-resume.vercel.app/#pierna-process)

</details>

<details>
<summary>📂 더 많은 작업 보기</summary>

- **Transformer from scratch** — PyTorch로 어텐션부터 직접 구현
- **[재활용 분류 앱](https://github.com/youngsuchoi0930/recycle_app)** — MobileNetV2 · TFLite · Flutter 온디바이스 분류기
- **한국어 TTS / Voice Cloning 탐색** — XTTS-v2 · OpenVoice V2 · MeloTTS 비교
- **음성 분류 (Dacon)** — MFCC · Mel-spectrogram 기반 오디오 전처리

</details>

---

### 🛠️ Tech Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=py,fastapi,flask,ts,react,tailwind,threejs,docker,gcp,postgres,mongodb,redis,vercel,githubactions,pytorch,git&perline=8" alt="Tech Stack" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Gemini-4E88F4?style=flat-square&logo=googlegemini&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white" />
  <img src="https://img.shields.io/badge/Claude-D97757?style=flat-square&logo=anthropic&logoColor=white" />
  <img src="https://img.shields.io/badge/Azure%20Speech-0078D4?style=flat-square&logoColor=white" />
  <img src="https://img.shields.io/badge/ElevenLabs-181717?style=flat-square&logoColor=white" />
  <img src="https://img.shields.io/badge/pgvector-336791?style=flat-square&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/Capacitor-119EFF?style=flat-square&logo=capacitor&logoColor=white" />
</p>

---

### 🐍 Contribution Snake

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/youngsuchoi0930/youngsuchoi0930/output/github-snake-dark.svg" />
    <img alt="github contribution snake" src="https://raw.githubusercontent.com/youngsuchoi0930/youngsuchoi0930/output/github-snake.svg" />
  </picture>
</p>

---

### 🌱 Now Building

```python
now_building = [
    "RAG 파이프라인 설계와 실패 분석 (Naive → Hybrid → Agentic)",
    "PyTorch로 Transformer 구조 직접 구현",
    "LoRA / QLoRA 로 LLM 파인튜닝",
    "MediaPipe 기반 멀티모달 (수어 · 제스처) 인식",
]
```

---

### 📫 Connect with Me

<p align="center">
  <a href="https://youngsu-resume.vercel.app">
    <img src="https://img.shields.io/badge/Resume-9184d9?style=for-the-badge&logoColor=white" />
  </a>
  <a href="mailto:y1692543@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/youngsuchoi0930">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
</p>

<p align="center">
  📧 <code>y1692543@gmail.com</code> · 📍 Seoul
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:9184d9,100:161826&height=110&section=footer" alt="footer" />
</p>
