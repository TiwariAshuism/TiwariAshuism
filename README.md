<!-- HEADER BANNER -->
<div align="center">

![header](https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1a2332,100:58a6ff&height=200&section=header&text=Ashutosh%20Kumar&fontSize=52&fontColor=ffffff&fontAlignY=38&desc=Full-Stack%20%7C%20Mobile%20%7C%20Backend%20Engineer&descSize=18&descAlignY=58&descColor=8b949e)

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&duration=2800&pause=800&color=58A6FF&center=true&vCenter=true&multiline=false&width=650&lines=Building+production-grade+systems+from+scratch+%F0%9F%9A%80;Go+BFF+%E2%86%92+Server-Driven+UI+%E2%86%92+Flutter+%2F+Kotlin;Wearable+DSP+%7C+BLoC+%7C+Hexagonal+Architecture;Clean+code%2C+strong+opinions%2C+shipped+products." alt="Typing SVG" />

<br/>

[![Profile Views](https://komarev.com/ghpvc/?username=TiwariAshuism&label=Profile+Views&color=58a6ff&style=flat-square)](https://github.com/TiwariAshuism)
&nbsp;
[![Twitter Follow](https://img.shields.io/twitter/follow/tiwari_ashuism?style=flat-square&logo=twitter&color=1DA1F2&labelColor=0d1117)](https://twitter.com/tiwari_ashuism)
&nbsp;
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/tiwari-ashuism)
&nbsp;
[![Medium](https://img.shields.io/badge/Medium-Follow-white?style=flat-square&logo=medium&logoColor=black)](https://medium.com/@tiwariashuism)

</div>

<br/>

---

## 👨‍💻 &nbsp;About Me

```go
package main

type Engineer struct {
    Name      string
    Location  string
    Focus     []string
    Expertise []string
    Currently string
    Contact   string
}

func main() {
    me := Engineer{
        Name:     "Ashutosh Kumar",
        Location: "Bengaluru, India 🇮🇳",
        Focus:    []string{"Mobile", "Backend", "Full-Stack", "DSP / Health Tech"},
        Expertise: []string{
            "Flutter (BLoC, Feature-First, MVI)",
            "Kotlin (Jetpack Compose, DSP, Signal Processing)",
            "Go (Hexagonal Architecture, Gin, Microservices)",
            "Server-Driven UI — BFF Pattern (Go → Flutter / Kotlin)",
            "Next.js · Firebase · PostgreSQL · Kafka · Redis",
        },
        Currently: "Building a medical-grade Health Wearable Platform",
        Contact:   "aksamtiwari@gmail.com",
    }
    _ = me
}
```

---

## 🏗️ &nbsp;Signature Systems

> Projects I've architected and built end-to-end. Not tutorials. Not clones. Production-grade systems.

<br/>

### 🎬 &nbsp;Cinema SDUI — Server-Driven UI Platform
> *Netflix-style server-driven UI engine · Go BFF + Android Kotlin/Jetpack Compose · ~19,700 lines · 97 files*

```
┌─────────────────────────────────────────────────────────────────────┐
│                   SERVER-DRIVEN UI  ARCHITECTURE                     │
├──────────────────────────┬──────────────────────────────────────────┤
│      GO BFF SERVER       │          ANDROID CLIENT                  │
│                          │                                          │
│  ┌──────────────────┐    │    ┌──────────────────────────────────┐  │
│  │  Component Tree  │────┼───▶│  Dynamic Renderer (Compose MVI)  │  │
│  │  (JSON payload)  │    │    │  Parses & renders any component  │  │
│  └──────────────────┘    │    └──────────────────────────────────┘  │
│                          │                                          │
│  ┌──────────────────┐    │    ┌──────────────────────────────────┐  │
│  │  Design Tokens   │────┼───▶│  Cinema Design System            │  │
│  │  Colors/Typo/    │    │    │  All visual props served by BFF  │  │
│  │  Spacing (BFF)   │    │    └──────────────────────────────────┘  │
│  └──────────────────┘    │                                          │
│                          │    ┌──────────────────────────────────┐  │
│  ┌──────────────────┐    │    │  WorkManager + SSE               │  │
│  │  SSE Stream      │────┼───▶│  Real-time UI updates            │  │
│  └──────────────────┘    │    └──────────────────────────────────┘  │
│                          │                                          │
│  Redis · OpenTelemetry   │    Hilt · Kotlin Coroutines              │
│  GitHub Actions CI/CD    │    Offline-first · WorkManager           │
└──────────────────────────┴──────────────────────────────────────────┘
```

**What makes it production-grade:**
- BFF owns **all visual properties** — zero hardcoded UI on client; layout changes ship without an app release
- **SSE-powered real-time updates** propagate component tree diffs to device instantly
- **Redis** caches component trees with TTL-based invalidation
- **OpenTelemetry** distributed tracing end-to-end: BFF → renderer
- **GitHub Actions CI/CD** with multi-stage Docker builds

`Go` `Gin` `Kotlin` `Jetpack Compose` `Hilt` `MVI` `Redis` `SSE` `OpenTelemetry` `WorkManager` `Docker` `GitHub Actions`

---

### 🫀 &nbsp;Health Wearable Platform
> *Medical-grade biometric engine · Flutter UI + Kotlin DSP + Firebase + TFLite · BLoC + Feature-First + MVI*

```
┌─────────────────────────────────────────────────────────────────────┐
│                   HEALTH WEARABLE  ARCHITECTURE                      │
├────────────────────────────┬────────────────────────────────────────┤
│      FLUTTER  (UI ONLY)    │      KOTLIN  (ALL COMPUTATION)         │
│                            │                                        │
│  ┌──────────────────────┐  │  ┌────────────────────────────────┐   │
│  │  BLoC State Machine  │  │  │  Pan-Tompkins  (5-stage ECG)   │   │
│  │  Feature-First arch  │◀─┼──│  Kalman ANC  (motion cancel)   │   │
│  │  Reliability-aware   │  │  │  Lomb-Scargle HRV periodogram  │   │
│  │  UI widgets          │  │  │  Quadratic SpO₂ calibration    │   │
│  └──────────────────────┘  │  └────────────────────────────────┘   │
│                            │                                        │
│  Flutter renders only.     │  ┌────────────────────────────────┐   │
│  No business logic.        │  │  ReliabilityEngine             │   │
│  No signal processing.     │  │  PersonalizationEngine         │   │
│                            │  │  AdaptiveSamplingScheduler     │   │
│                            │  │  TimeAlignedBuffer             │   │
│                            │  │  RrIntervalCorrector           │   │
│                            │  │  MLLifecycleManager (TFLite)   │   │
│                            │  │  ObservabilityPipeline         │   │
│                            │  │  BatchOrchestrator (Cloud Fn)  │   │
│                            │  └────────────────────────────────┘   │
│      Firebase  ·  Realtime DB  ·  Cloud Functions  ·  Auth         │
│      Method Channel Contract :  Flutter  ↔  Kotlin                 │
└────────────────────────────┴────────────────────────────────────────┘
```

**Key engineering decisions:**
- **Hard boundary**: Flutter renders only — no DSP or business logic leaks into Dart
- **Kalman filter ANC** cancels accelerometer-correlated motion artifacts from PPG in real-time
- **Lomb-Scargle periodogram** for HRV on non-uniformly sampled RR intervals
- **Method Channel contracts** define the Flutter ↔ Kotlin interface — typed, versioned, testable

`Flutter` `Kotlin` `Firebase` `TFLite` `BLoC` `BLE` `Kalman Filter` `Pan-Tompkins` `DSP` `MVI`

---

### ⚙️ &nbsp;Hexagonal Go Microservice
> *Production backend · ~3,500 lines · 33 files · full observability stack*

```
Gin Router → JWT Auth → Domain Layer → Port Interfaces
     ↓               ↓           ↓              ↓
Rate Limit     Redis Cache   PostgreSQL    Kafka Events
  Circuit Breaker (Retry + Backoff)  ↔  Distributed Lock
OpenTelemetry Traces  →  Prometheus Metrics  →  Grafana
```

`Go` `Gin` `PostgreSQL` `Redis` `Kafka` `JWT` `Circuit Breaker` `OpenTelemetry` `Prometheus` `Docker`

---

### 📊 &nbsp;CryptLedger — CRED-Inspired Crypto Tracker
> *Premium dark Flutter app · BLoC · Feature-First MVC · GetIt · GoRouter · NeoPopButton · 38+ Dart files*

Net worth dashboard · Transaction ledger · Portfolio donut chart · Tax breakdown · AI insight cards

`Flutter` `BLoC` `GetIt` `GoRouter` `NeoPopButton` `Feature-First` `Dart`

---

### 📈 &nbsp;AI Day Trading Platform
> *Full-stack learning platform · Next.js 14 · FastAPI · PostgreSQL · OpenAI*

Candle-by-candle replay engine · AI coaching chat · Virtual trade simulation · Behavioral pattern tracking (FOMO, overtrading) · Discipline scoring

`Next.js` `FastAPI` `PostgreSQL` `OpenAI` `Docker`

---

## 🛠️ &nbsp;Tech Stack

<table>
<tr>
<td valign="top" width="33%">

**📱 Mobile**

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-4285F4?style=flat-square&logo=jetpack-compose&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white)

</td>
<td valign="top" width="33%">

**⚙️ Backend**

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

</td>
<td valign="top" width="33%">

**🌐 Frontend**

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

</td>
</tr>
<tr>
<td valign="top">

**🗄️ Data & Messaging**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apache-kafka&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)

</td>
<td valign="top">

**🚀 DevOps & Observability**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)

</td>
<td valign="top">

**🤖 AI / ML**

![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![TFLite](https://img.shields.io/badge/TFLite-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)

</td>
</tr>
</table>

---

## 📊 &nbsp;GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=TiwariAshuism&show_icons=true&theme=github_dark&hide_border=true&count_private=true&bg_color=0d1117&title_color=58a6ff&icon_color=58a6ff&text_color=8b949e" height="170" />
&nbsp;
<img src="https://github-readme-stats.vercel.app/api/top-langs?username=TiwariAshuism&layout=compact&theme=github_dark&hide_border=true&langs_count=8&bg_color=0d1117&title_color=58a6ff&text_color=8b949e" height="170" />

<br/><br/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=TiwariAshuism&theme=github-dark-blue&hide_border=true&background=0d1117&stroke=58a6ff&ring=58a6ff&fire=ff6b6b&currStreakLabel=58a6ff" />

</div>

---

## 🏆 &nbsp;Trophies

<div align="center">

[![Trophies](https://github-profile-trophy.vercel.app/?username=TiwariAshuism&theme=gitdimmed&no-frame=true&row=1&column=6&margin-w=10)](https://github.com/ryo-ma/github-profile-trophy)

</div>

---

## 📝 &nbsp;Latest Writing

> 📌 Engineering deep-dives → [ashu-blog.vercel.app/blog](https://ashu-blog.vercel.app/blog) &nbsp;·&nbsp; [medium.com/@tiwariashuism](https://medium.com/@tiwariashuism)

---

## 🤝 &nbsp;Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/tiwari-ashuism)
[![Twitter](https://img.shields.io/badge/Twitter_/_X-000000?style=for-the-badge&logo=x&logoColor=white)](https://twitter.com/tiwari_ashuism)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/tiwari_ashuism)
[![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@tiwariashuism)
[![Blog](https://img.shields.io/badge/Blog-FF5722?style=for-the-badge&logo=rss&logoColor=white)](https://ashu-blog.vercel.app/blog)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:aksamtiwari@gmail.com)

</div>

<br/>

<!-- FOOTER BANNER -->
![footer](https://capsule-render.vercel.app/api?type=waving&color=0:58a6ff,50:1a2332,100:0d1117&height=100&section=footer)
