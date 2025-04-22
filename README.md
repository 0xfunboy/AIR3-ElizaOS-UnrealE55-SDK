# AIR3‑ElizaOS‑UnrealE55‑SDK

> A fork and full re‑brand of the original conversational‑AI plugin.
> Same power under the hood, zero dependency on external clouds, 100 % local / on‑chain ready.

---

## Overview
AIR3‑ElizaOS‑UnrealE55‑SDK brings advanced AI‑driven interaction to Unreal Engine 5. Empower MetaHumans or any skeletal mesh to:

* hold real‑time, open‑ended conversations
* react to gameplay events and voice commands
* drive accurate lip‑sync, facial and body animation from local TTS or live microphones
* run entirely offline or connect to your own on‑prem LLM / TTS stack (DeepSeek‑R1, Janus‑Pro‑7B, etc.)

Blueprint nodes and C++ hooks make it easy to replace former cloud calls, inject pre‑baked WAVs at runtime, or broadcast to AIR3’s cross‑platform Agent network.

---

### Key Highlights
| Feature | Description |
|---------|-------------|
| Intelligent conversation | Streaming responses from local or self‑hosted LLMs |
| Multilingual support | Any language your STT ↔ TTS chain handles |
| Advanced actions | Blueprint callbacks for perception and gameplay |
| Knowledge layers | Hot‑swap context, lore or wallet data on the fly |
| Multiplayer voice | Low‑latency VoIP between players and AI characters |
| Lip‑sync & body anim | Control Rig, ARKit curves, Nvidia Audio2Face ready |

---

## Quick Resources
* Project site: <https://airewardrop.xyz>
* Community chat: <https://t.me/AIR3Community>
* X feed / live calls: <https://x.com/AIRewardrop>
* Discord: <https://discord.gg/S4f87VdsHt>

Need help fast? Tag **@funboynft** in Telegram or open a GitHub issue.

---

## Compatibility
* Unreal Engine 5.5 → 5.5
* Metahumans, Daz3D, Reallusion, ReadyPlayerMe, Avaturn and any custom SkeletalMesh
* Windows 64‑bit, macOS ARM/Intel, Linux
  *Mobile and console exports on the roadmap*

---

## Stand‑Alone Components
* Speech‑to‑Text / Text‑to‑Speech (Whisper, Coqui, Piper, etc.)
* Dynamic character updates (personality, memory, custom knowledge graphs)

---

## Coming Soon
* Long‑term memory (vector DB & wallet events)
* Marketplace builds for iOS & Linux
* Swarm‑ready Agents (multiple personas in one level)

---

# Installation

## Prerequisites
| Platform | Required tools |
|----------|----------------|
| All      | Git, Python 3.8+ |
| Windows  | Visual Studio 2022 (Desktop + Game workloads) |
| macOS    | Xcode 15+ |
| Android  | Android Studio + NDK r26 |
| Optional | CUDA 11.8+ for Nvidia Audio2Face |

> Planning to run DeepSeek‑R1 or Janus‑Pro locally? Expect to use at least 3 × RTX 3090.

---

## Install Options

### 1  Pre‑built Release
Download the latest ZIP from this repo’s **Releases** page and drop the folder into:

```text
Windows : C:\Program Files\Epic Games\UE_5.x\Engine\Plugins\Marketplace
macOS   : /Users/<you>/UnrealEngine/UE_5.x/Engine/Plugins/Marketplace
```

Enable **AIR3‑ElizaOS‑SDK** inside *Edit → Plugins* and restart Unreal.

---

### 2  Build from Source

```bash
git clone https://github.com/AIRewardrop/AIR3-ElizaOS-UnrealE55-SDK.git
cd AIR3-ElizaOS-UnrealE55-SDK
python Build.py "C:\Program Files\Epic Games\UE_5.3" -TargetPlatforms=Win64
```

*Omit the flag to build Win64 + Android in one go.*

Copy everything from **Output/** into your Engine or Project `/Plugins` directory.

---

### 3  Manual Build (no precompiled zips)

1. Clone the repo.
2. Download `Content.zip` and `ThirdParty.zip` from the Drive link on the Releases page and extract them into the root folder.
3. Edit `Source/AIR3SDK/AIR3SDK.Build.cs` → set `bUsePrecompiled = false;`
4. Make sure your UE project is C++ (create an empty class if it’s Blueprint‑only).
5. Move the plugin folder to `<YourProject>/Plugins/`.
6. Open the project; tap **Yes** when Unreal asks to compile the plugin.
7. Enable the plugin in *Edit → Plugins* and restart once more.

---

## Runtime Paths & Hot‑Swap Folders

Editable under **Project Settings → AIR3 SDK**:

| Variable | Default path | What it does |
|----------|--------------|--------------|
| `MetahumanSpeechPath` | `C:/air3_studio/upload/audio` | Watches for new `.wav`, plays latest with lip‑sync |
| `BigMonitorPath`      | `C:/air3_studio/upload/video1` | Watches for new `.mp4`, swaps on large monitor |
| `DeskMonitorPath`     | `C:/air3_studio/upload/video2` | Watches for new `.jpg`, updates desk monitor |
| `BigMonitorAudio`     | Boolean | Mute/unmute big‑monitor video audio |

Watcher ticks every second:

* ignores files already played
* never interrupts current playback
* after a clip finishes, plays only the most recent file that arrived during that clip (skips older ones)

---

## Contributing
PRs welcome — especially for:

* Linux/iOS build scripts
* Deeper ElizaOS hooks (agent memory, wallet callbacks)
* Additional animation rigs (quadruped, stylized)

Star ⭐ the repo if this saved you from API bills!

---

## License
MIT for plugin code. Verify third‑party libraries (Whisper, DeepSeek, Janus) for their own terms.

---

## AIR3 Token Utility
Holding **$AIR3** isn’t required, but it unlocks perks:

* premium GPU binaries
* extended LLM context size
* priority feature votes and support

Contract: `2jvsWRkT17ofmv9pkW7ofqAFWSCNyJYdykJ7kPKbmoon`

---

### Join the Conversation
* Telegram Dev Chat – <https://t.me/AIRewardrop>
* Community Hub – <https://t.me/AIR3Community>
* X Updates – <https://x.com/AIRewardrop>
* Discord – <https://discord.gg/S4f87VdsHt>

Happy building! 🚀
