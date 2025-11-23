# MeetProject

## 프로젝트 개요
MeetProject는 React 기반 클라이언트와 Spring Boot 기반 Signal 서버를 통해 WebRTC 1:1/그룹 통신을 지원하는 실시간 화상 회의 애플리케이션입니다.<br>
주요 기능으로는 참가자 관리, WebRTC 연결, 화면 공유, 채팅, 손들기 기능을 포함하며, STOMP(WebSocket)를 기반으로 Signal 서버와 클라이언트 간 실시간 통신을 처리합니다.<br>

## 구현 환경
- 서버: Spring Boot + STOMP/WebSocket
- 클라이언트: Next.js + TypeScript + STOMP.js

## 주요 기능

- 참가자 데이터 관리
    - 생성된 roomID 관리
    - 참여 중인 userID 관리, 참여자 이름 관리
- WebSocket을 통한 실시간 통신 관리
    - connect에 따른 userID 단순 생성 및 등록/반환
    - join에 따른 해당 roomID의 참가자 id 반환
    - offer에 따른 참가들에게 정보 전달
    - answer에 따른 정보 전달
    - 채팅 메세지 브로드캐스트 및 1:1 전송
- 1:1 WebRTC 연결
    - 장치 변경
    - 화면 공유
