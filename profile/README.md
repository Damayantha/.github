<div align="center">

<a href="https://github.com/PersonaliAI">
  <img src="https://raw.githubusercontent.com/PersonaliAI/.github/master/profile/assets/header-banner.svg" alt="PersonaliAI Header Banner" width="100%" />
</a>

<br/>

### **Open-Source Conversational AI · Real-Time Multimodal Voice · Ubiquitous SDKs**

*Empowering developers and organizations with production-grade conversational infrastructure — from web widgets and cross-platform mobile SDKs to real-time voice agents and autonomous personal assistants.*

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Docker](https://img.shields.io/badge/Docker-Self--Hostable-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://github.com/PersonaliAI/chatty)
[![LiveKit](https://img.shields.io/badge/LiveKit-WebRTC_Voice-00D2B8?style=for-the-badge&logo=webrtc&logoColor=white)](https://livekit.io)
[![Next.js 15](https://img.shields.io/badge/Next.js-15_App_Router-000000?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org)
[![Cross Platform](https://img.shields.io/badge/Platforms-Web_·_iOS_·_Android_·_RN_·_Flutter-8b5cf6?style=for-the-badge)](https://docs.chatty.personaliai.com)

<br/>

**[🌐 Official Website](https://chatty.personaliai.com)** &nbsp;•&nbsp;
**[📚 Documentation](https://docs.chatty.personaliai.com)** &nbsp;•&nbsp;
**[💬 Chatty Cloud](https://chatty.personaliai.com)** &nbsp;•&nbsp;
**[📦 Integration SDKs](#-ubiquitous-integration-sdk-matrix)** &nbsp;•&nbsp;
**[🤝 Contributing](#-contributing--community)**

---

</div>

<br/>

## 🌟 Overview

**PersonaliAI** builds modular, open-source AI infrastructure that turns state-of-the-art LLMs into real-time conversational agents. Our ecosystem bridges the gap between web platforms, native mobile applications, telephony/messaging channels, and autonomous voice agents.

Whether you need a **drop-in AI customer support widget**, an **interactive real-time voice agent**, or **full-duplex mobile SDKs**, PersonaliAI provides a cohesive, self-hostable foundation with zero vendor lock-in.

<br/>

---

## 🏛️ Ecosystem & System Architecture

<div align="center">
  <img src="https://raw.githubusercontent.com/PersonaliAI/.github/master/profile/assets/architecture-diagram.svg" alt="PersonaliAI Architecture Diagram" width="100%" />
</div>

<br/>

### 1. Core Conversational Platforms
* **[Chatty (`PersonaliAI/chatty`)](https://github.com/PersonaliAI/chatty)** — Next-generation AI customer support and sales automation platform. Features RAG over documents/websites, LiveKit-powered real-time voice calls, live human agent takeover, conversational meeting scheduling (Google Meet & Zoom), lead capture, and CSAT.
* **[Kin (`PersonaliAI/kin`)](https://github.com/PersonaliAI/kin)** — Open-source personal AI assistant with persistent long-term memory, voice calls, and real autonomous tool actions across calendar, email, and social services.
* **[AI Voice Agents (`PersonaliAI/ai-voice-agents`)](https://github.com/PersonaliAI/ai-voice-agents)** — Real-time WebRTC audio worker bridging live calls over Telegram and WhatsApp voice notes, backed by an ultra-fast VAD/STT/LLM/TTS pipeline.

<br/>

---

## 📱 Ubiquitous Integration SDK Matrix

Every SDK is designed with **100% Web Widget Parity** via our hardened **Script Method** (isolated WebView embedding `/embed/{botId}` with raw alert suppression, font-zoom isolation, and full bridge protocol) alongside high-performance **Native UI Components**.

| Platform | Repository | Package / Artifact | Key Features |
|:---|:---|:---|:---|
| **Web (Vanilla & React)** | [**`PersonaliAI/chatty`**](https://github.com/PersonaliAI/chatty) | `<script src=".../widget.js">` | Isolated Shadow DOM, zero iframe, responsive design, 100% vector typography |
| **React Native / Expo** | [**`chatty-react-native-sdk`**](https://github.com/PersonaliAI/chatty-react-native-sdk) | [`@personaliai/react-native`](https://www.npmjs.com/package/@personaliai/react-native) | `ChattyEmbedView` + `ChattyChatView`, LaTeX math fork, full theming tokens, zero-native peer deps |
| **Flutter / Dart** | [**`chatty-flutter-sdk`**](https://github.com/PersonaliAI/chatty-flutter-sdk) | [`chatty_flutter`](https://pub.dev) | `ChattyEmbedScreen` + `ChattyLauncher`, CommonMark tables, `$inline$` & `$$block$$` LaTeX math |
| **Android (Kotlin)** | [**`chatty-android-sdk`**](https://github.com/PersonaliAI/chatty-android-sdk) | `com.github.PersonaliAI:chatty-android-sdk` | Jetpack Compose, `ChattyEmbedView`, androidx.emoji2 picker, JitPack distribution |
| **iOS (Swift)** | [**`chatty-ios-sdk`**](https://github.com/PersonaliAI/chatty-ios-sdk) | Swift Package Manager | SwiftUI native chat view, `ChattyEmbedView`, audio recording session management |
| **WordPress** | [**`chatty-wordpress-plugin`**](https://github.com/PersonaliAI/chatty-wordpress-plugin) | Official WP Plugin Directory | Zero-code setup, automatic domain authorization, Gutenberg block & shortcode |

<br/>

---

## ⚡ Drop-in Integration in 30 Seconds

<details open>
<summary><strong>🌐 Web & HTML (One-line embed)</strong></summary>

```html
<!-- Drop before </body> on any webpage -->
<script 
  src="https://chatty.personaliai.com/widget.js" 
  data-id="YOUR_BOT_UUID" 
  defer>
</script>
```
</details>

<details>
<summary><strong>⚛️ React Native / Expo</strong></summary>

```tsx
import React from "react";
import { SafeAreaView } from "react-native";
import { ChattyEmbedView } from "@personaliai/react-native";

export default function SupportScreen() {
  return (
    <SafeAreaView style={{ flex: 1 }}>
      <ChattyEmbedView
        botId="YOUR_BOT_UUID"
        onMicPermissionNeeded={() => console.log("Microphone permission needed")}
        onLocationPermissionNeeded={() => console.log("Location permission needed")}
      />
    </SafeAreaView>
  );
}
```
</details>

<details>
<summary><strong>💙 Flutter</strong></summary>

```dart
import 'package:flutter/material.dart';
import 'package:chatty_flutter/chatty_flutter.dart';

class SupportScreen extends StatelessWidget {
  const SupportScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return const Scaffold(
      body: SafeArea(
        child: ChattyEmbedScreen(botId: 'YOUR_BOT_UUID'),
      ),
    );
  }
}
```
</details>

<details>
<summary><strong>🤖 Android (Jetpack Compose)</strong></summary>

```kotlin
import com.personaliai.chatty.ChattyEmbedView

@Composable
fun SupportScreen() {
    ChattyEmbedView(
        botId = "YOUR_BOT_UUID",
        modifier = Modifier.fillMaxSize()
    )
}
```
</details>

<details>
<summary><strong>🍎 iOS (SwiftUI)</strong></summary>

```swift
import SwiftUI
import ChattySDK

struct SupportView: View {
    var body: some View {
        ChattyEmbedView(botId: "YOUR_BOT_UUID")
            .edgesIgnoringSafeArea(.all)
    }
}
```
</details>

<br/>

---

## 💎 Core Engineering Principles

```
  ┌───────────────────────┐   ┌───────────────────────┐   ┌───────────────────────┐
  │   🎙️ Real-Time Audio  │   │  🛡️ "Reflect, Never"  │   │   📐 Math & Markdown  │
  │     LiveKit WebRTC    │   │      Permissions      │   │   LaTeX + CommonMark  │
  │   < 400ms Turn Latency│   │  Zero unsolicited UI  │   │   Remark & KaTeX GFM  │
  └───────────────────────┘   └───────────────────────┘   └───────────────────────┘
```

1. **Full-Duplex Real-Time Voice**: Powered by LiveKit WebRTC, Cartesia, ElevenLabs, and Deepgram/Whisper. Users can interrupt the AI mid-sentence with natural barge-in detection.
2. **"Reflect, Never Request" Permission Contract**: Our SDKs never pop unsolicited OS permission dialogs. They inspect granted status and fire contextual callbacks (`onMicPermissionNeeded`, `onLocationPermissionNeeded`) so your app maintains complete UI ownership.
3. **Collateral-Free LaTeX Math & Markdown**: Native CommonMark parser + KaTeX equation tokenizer isolates math formulas (`$E = mc^2$`) from markdown syntax collisions.
4. **Absolute Data Sovereignty**: Self-host the entire platform with a single `docker compose up -d`. All embeddings, conversation logs, and customer metadata stay inside your private network.

<br/>

---

## 🛠️ Technology Stack

<div align="center">

| Layer | Technologies |
|:---|:---|
| **Frontend & Dashboard** | ![Next.js](https://img.shields.io/badge/Next.js_15-000000?style=flat-square&logo=next.js&logoColor=white) ![React](https://img.shields.io/badge/React_19-20232A?style=flat-square&logo=react&logoColor=61DAFB) ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_v4-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white) |
| **Backend & Voice Core** | ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat-square&logo=fastapi) ![Python](https://img.shields.io/badge/Python_3.12-3776AB?style=flat-square&logo=python&logoColor=white) ![LiveKit](https://img.shields.io/badge/LiveKit_WebRTC-00D2B8?style=flat-square&logo=webrtc&logoColor=white) ![Silero VAD](https://img.shields.io/badge/Silero_VAD-FF6F00?style=flat-square) |
| **Mobile & Multi-Platform**| ![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white) ![React Native](https://img.shields.io/badge/React_Native-61DAFB?style=flat-square&logo=react&logoColor=black) ![Kotlin](https://img.shields.io/badge/Kotlin_Compose-7F52FF?style=flat-square&logo=kotlin&logoColor=white) ![Swift](https://img.shields.io/badge/Swift_SwiftUI-FA7343?style=flat-square&logo=swift&logoColor=white) |
| **Database & Vector RAG** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white) ![pgvector](https://img.shields.io/badge/pgvector-336791?style=flat-square) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) |
| **Infrastructure & DevOps**| ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white) ![Firebase Hosting](https://img.shields.io/badge/Firebase_App_Hosting-FFCA28?style=flat-square&logo=firebase&logoColor=black) |

</div>

<br/>

---

## 🤝 Contributing & Community

We believe the future of conversational AI is open, transparent, and developer-first. Contributions are welcome across all repositories!

* 💡 **Ideas & Discussions**: Share architecture suggestions and use cases in our Discussions.
* 🐛 **Bug Reports**: Open an issue on the relevant repository with reproduction steps.
* 🛠️ **Pull Requests**: Review our contribution guidelines and submit your PRs.

<br/>

<div align="center">

Made with ❤️ by the **[PersonaliAI](https://github.com/PersonaliAI)** Team

*© 2026 PersonaliAI. All projects licensed under [MIT](LICENSE).*

</div>
