# CameraFeedr 🔒

> *"I love privacy, but some people just don't get it—they barge into my room without even knocking. This simple project helps you avoid that with the help of camera detection using MediaPipe. I hope you find it useful."*

A local-first, privacy-respecting room entry alert system built by a Year 9 student. No cloud. No data leaves your LAN. Runs entirely in-browser using on-device AI.

---

## 🎯 What It Does

- **Feeder** (phone/iPad): Captures camera feed, runs MediaPipe Pose Landmarker on-device to detect standing/moving people, sends live video + detection events over WebRTC/WebSocket
- **Receiver** (PC): Displays live video feed with skeleton overlay, status panel, and timestamped event log in a security-console HUD
- **Server** (Node.js): Lightweight HTTPS relay for WebRTC signaling and WebSocket events—no video processing on server

## ⚠️ Critical Requirements

| Requirement | Details |
|-------------|---------|
| **Python Version** | Python 3.11 or 3.12 only (3.14 is unsupported) |
| **Node.js** | v18+ LTS |
| **Browser** | Chrome/Edge (desktop), Safari (iPad with certificate trust) |
| **Network** | All devices on same LAN; Windows network profile set to **Private** |
| **HTTPS** | Required for `getUserMedia`; use mkcert for local trusted certs |

## 🚀 Setup Guide

### 1. Install Dependencies
```powershell
cd "$env:USERPROFILE\Downloads\camera-detector-app\camera-detector"
npm install
