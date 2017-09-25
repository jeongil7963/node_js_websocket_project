
# socket.io
    HTTP는 무상태 프로토콜(stateless protocol)으로 어떠한 이전 요청과도 무관한 각각의 요청을 독립적인 트랜잭션으로 취급하는 통신 프로토콜이다. 
    
    이러한 HTTP의 한계에서 벗어나 Node.js에서 손쉽게 Real-time communication(RTC, 실시간 양방향 통신) 웹 애플리케이션을 작성할 수 있는 
    
    Socket.io를 간단한 채팅 애플리케이션 작성을 통해 알아본다.

## 1. WebSocket

    WebSocket은 사용자의 브라우저와 서버 사이의 동적인 양방향 연결 채널을 구성하는 HTML5 프로토콜이다. 
    
    WebSocket API를 통해 서버로 메시지를 보내고 요청 없이 응답을 받아오는 것이 가능하다.

    HTTP는 클라이언트에 의해 초기화되기 때문에 서버가 변경사항을 클라이언트에게 알릴 수 있는 방법이 없다.
    
    하지만 WebSocket의 연결은 HTTP 통신과는 다르게 클라언트가 특정 주기를 가지고 Polling하지 않아도 변경된 사항을 시기 적절하게 전달할 수 있는 지속적이고 완전한 양방향 연결 스트림을 만들어 주는 기술이다.

    이러한 특성으로 인해 WebSocket은 서버의 데이터를 클라이언트에 즉시 전달할 수 있는 실시간 애플리케이션 작성에 매우 효과적인 프로토콜이다.

    WebSocket을 사용하여 Node.js 기반 서버와 통신이 가능한 예제를 작성한다.

    먼저 클라이언트(브라우저) WebSocket을 구현한다. 
    
    루트 디렉터리에 index.html을 작성한다.

    다음은 ws 모듈을 사용하여 Node.js 기반 서버를 구현한다.

            > $ mkdir native-websocket && cd native-websocket
            > $ npm init --yes
            > $ npm install ws --save
    
    루트 디렉터리에 server.js을 작성한다.

    서버를 실행한다.

        > $ node server
    
    브라우저에서 index.html을 열면 콘솔에서 메시지를 확인할 수 있다.

## 2. Socket.io

    HTML5 WebSocket은 매우 유용한 기술이지만 오래된 브라우저의 경우 지원하지 않는 경우가 있다.

    caniuse-websocket

    www.caniuse.com

    브라우저 간 호환이나 이전 버전 호환을 고려하여 Node.js를 위한 강력한 Cross-platform WebSocket API인 Socket.io를 사용하는 것이 바람직하다.

## 3. Install

    프로젝트 루트 디렉터리를 생성하고 Socket.io를 인스톨한다.

        > $ mkdir socketio-chat && cd socketio-chat
        > $ npm init --yes
        > $ npm install --save --save-exact socket.io express
    
    package.json의 내용은 아래와 같다. Node.js 6.4.0를 사용하였다.

        > {
        > "name": "socketio-chat",
        > "version": "1.0.0",
        > "scripts": {
        >     "start": "node app"
        > },
        > "dependencies": {
        >     "express": "4.14.0",
        >     "socket.io": "1.4.8"
        > }
        > }