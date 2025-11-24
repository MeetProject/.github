# MeetProject

## 프로젝트 개요
MeetProject는 React 기반 클라이언트와 Spring Boot 기반 Signal 서버를 통해 WebRTC 1:1/그룹 통신을 지원하는 실시간 화상 회의 애플리케이션입니다.<br>
주요 기능으로는 참가자 관리, WebRTC 연결, 화면 공유, 채팅, 손들기 기능을 포함하며, STOMP(WebSocket)를 기반으로 Signal 서버와 클라이언트 간 실시간 통신을 처리합니다.<br>

## 구현 환경
### Frontend
- Next.js 14 (App Router)
- TypeScript
- Zustand
- WebRTC API (getUserMedia, RTCPeerConnection)
- STOMP.js + SockJS

### Backend
- Spring Boot 3
- WebSocket(STOMP)
- SimpleBroker
- JDK 21

```
root
 ├── signal-server/       # WebRTC Signaling Server (Spring Boot)
 └── web-client/          # WebRTC Client (Next.js, React, WebRTC API)
```

```
Client
 ├─ WebRTC API (PeerConnection / MediaStream)
 ├─ STOMP over WebSocket
        ↓
Signal Server (Spring Boot)
 ├─ Join / Leave Orchestrator
 ├─ Offer / Answer / ICE Routing
 ├─ ScreenShare Management
 ├─ Chat / HandUp Broadcast
 └─ Message Broker (SimpleBroker)
        ↓
Client (Single / Broadcast)
```

## 주요 기능

- WebRTC 기본 기능
    - P2P 연결 생성 (STUN 사용)
    - Offer / Answer / ICE Candidate 교환
    - 카메라 / 마이크 / 화면 공유 스트림 전송
- 신호(Signaling) 서버 기능
    - 클라이언트 연결 및 userId 발급
    - Join/Leave 이벤트 관리
    - Offer / Answer / ICE Candidate 중계
    - 화면 공유 사용자 상태 관리
    - 채팅 / 손들기 / 장치 On-Off 브로드캐스트
- 클라이언트 기능
    - PeerConnection 생성 및 매핑
    - 참가자 MediaStream 관리
    - 장치 선택(카메라, 마이크, 스피커)
    - 손들기 UI, 화면 공유 토글
    - 채팅 전송 및 실시간 표시
    - Zustand 기반 스토어 관리
 
