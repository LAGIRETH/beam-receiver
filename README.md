# 🚀 BEAM - Decentralized P2P Data Transport Protocol

## 💀 THE REVENGE

**Beam is a weapon against corporate subscriptions.**

- ❌ WeTransfer? **Killed.** (File Beam Transporter)
- ❌ Ngrok? **Killed.** (Secure Proxy Tunnel)
- ❌ Dropbox? **Killed.** (Beam Sync)

**Zero servers. Zero subscriptions. Zero corporate scanning. Pure P2P.**

---

## ⚡ FEATURES

### 📦 **1. File Beam Transporter**
Transfer files directly to a browser's hard drive at maximum speed.

**Why it's better than WeTransfer:**
- ✅ **No file size limits** - Transfer 100GB+ files
- ✅ **No ads** - Clean, brutalist interface
- ✅ **No waiting** - Direct P2P connection
- ✅ **No server storage** - Files go directly from your PC to theirs
- ✅ **Zero installation** - Receiver just opens a browser link
- ✅ **Real-time progress** - See speed (MB/s) and ETA
- ✅ **Flow control** - Handles massive files without crashing browsers

**Speed:** Limited only by your upload bandwidth. If you have 100 Mbps upload, you get ~12 MB/s transfer speed.

---

### 🌐 **2. Secure Proxy Tunnel**
Expose localhost services to the internet via WebRTC.

**Why it's better than Ngrok:**
- ✅ **$0 forever** - No $8/month subscription
- ✅ **No time limits** - Keep tunnels open as long as you want
- ✅ **No bandwidth caps** - Unlimited data transfer
- ✅ **No ads or branding** - Clean, professional
- ✅ **Multiplexed connections** - Handle multiple simultaneous requests
- ✅ **Custom binary protocol** - Efficient 5-byte header system
- ✅ **Connection tracking** - Monitor bytes sent/received per connection
- ✅ **Idle cleanup** - Automatically closes stale connections

**Use case:** Show your localhost:3000 React app to a client in another country. They open a link, their browser becomes a gateway to your local server.

---

### 🔄 **3. Beam Sync**
Real-time folder synchronization between PCs.

**Why it's better than Dropbox:**
- ✅ **No storage limits** - Sync as much as your hard drives can hold
- ✅ **No monthly fees** - $0 forever
- ✅ **No corporate scanning** - Your files never touch a server
- ✅ **Real-time sync** - Changes propagate instantly via WebRTC
- ✅ **Bidirectional** - Both PCs can modify files
- ✅ **Delete propagation** - Delete on PC-A, deletes on PC-B
- ✅ **Recursive watching** - Monitors subfolders automatically
- ✅ **Chunked transfer** - 64KB chunks with custom binary protocol

**Use case:** Sync your work folder between home and office PCs without trusting any cloud provider.

---

## 🛡️ SECURITY

- **End-to-End Encrypted** - WebRTC uses DTLS/SRTP encryption
- **Zero Middleman** - Data travels directly P2P
- **No Server Storage** - Files never touch our infrastructure (we have none)
- **Open Source** - Audit the code yourself

---

## 🏗️ ARCHITECTURE

### The Magic: WebRTC + ntfy.sh

**How it works without servers:**

1. **Go CLI** generates a WebRTC Offer (cryptographic handshake)
2. **ntfy.sh** (free push notification service) temporarily stores the Offer
3. **Browser** polls ntfy.sh, grabs the Offer, generates an Answer
4. **Browser** posts Answer back to ntfy.sh
5. **Go CLI** grabs Answer, completes the handshake
6. **P2P tunnel established** - ntfy.sh is no longer involved
7. **Data flows directly** from PC to PC via WebRTC

**Cost:** $0.00 (ntfy.sh is free, GitHub Pages is free, STUN servers are free)

---

## 📊 PERFORMANCE

| Feature | Speed | Limit |
|---------|-------|-------|
| File Beam | Your upload bandwidth | None (tested 100MB+) |
| Proxy Tunnel | Your upload bandwidth | Unlimited connections |
| Beam Sync | Real-time | Unlimited files |

---

## 🎯 USE CASES

1. **Developers** - Show localhost apps to clients without deploying
2. **Designers** - Send massive PSD/AI files to clients instantly
3. **Teams** - Sync work folders between offices without cloud
4. **Privacy advocates** - Transfer files without corporate surveillance
5. **Students** - Share project files without WeTransfer ads

---

## 🔧 TECH STACK

- **Language:** Go (Golang) - Single binary, blazing fast
- **WebRTC:** Pion - Industry-standard Go WebRTC implementation
- **Signaling:** ntfy.sh - Free, open-source push notifications
- **File Watching:** fsnotify - Cross-platform filesystem events
- **UI:** Terminal-based brutalist design
- **Receiver:** Vanilla HTML/JS (no frameworks, no bloat)

---

## 🚀 GETTING STARTED

See [USAGE.md](USAGE.md) for detailed instructions.

**Quick start:**
```bash
# Install dependencies
go get github.com/pion/webrtc/v4
go get github.com/fsnotify/fsnotify

# Build
go build -o beam.exe

# Run
.\beam.exe
