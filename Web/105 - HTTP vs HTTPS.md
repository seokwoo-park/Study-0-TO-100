# HTTP vs HTTPS

## About

구글에 접속해 주소창의 주소를 복사하면 다음과 같이 복사가된다.

> https://www.google.com/

맨 앞에 https라는 문자가 붙어있는 걸 볼 수 있는데
가끔은 http라고도 붙어있기도 하다.
그럼 이 둘의 차이는 무엇일까?
<br/>
<br/>
<br/>

<img src="https://media.vlpt.us/images/mactto3487/post/b1c53eeb-4031-47b5-ac54-f59aeb893493/image.png" width=100%>
<br/>
<br/>

## HTTP
### (HyperText Transfer Protocol)
<br/>

URL 맨 앞에 http가 붙어있다는 건
서버와 클라이언트 통신을 할 때 HTTP 방식을 이용하겠다는 의미이다.

HTTP는 HyperTest Transfer Protocol의 약자로 인터넷에서 웹 서버와 사용자의 인터넷 웹 브라우저 사이에 하이퍼텍스트 (HyperText) 문서를 전송하기 위한 통신규약(protocol)이다.

HTTP는 정보를 텍스트로 주고 받는다. 단순 텍스트를 주고 받기 때문에 네트워크에서 전송 신호를 인터셉트하는 경우 원하지 않는 데이터 유출이 발생할 수도 있다.

예시로 우리가 특정 은행사이트에 접속해 로그인하는 경우
아무런 암호화 없이 HTTP 메시지를 만들어 전송했을 때
중간에서 누군가 이 HTTP 메시지를 가로챈다면
내 아이디와 비밀번호가 그대로 가로챈 사람한테 노출되게 된다.

따라서 만약에 중간에 탈취당하더라도 암호화를 해서 알아볼 수 없게 만들어야한다.
HTTPS가 바로 이 문제를 해결하기 위해 등장한 개념이다.

## HTTPS
### (HyperText Transfer Protocol Secure)
<br/>

약자에서 볼 수 있 듯 HTTPS는 HTTP 방식에 Secure(보안)을 추가한 개념이다.
HTTPS를 통해 우리는 데이터를 안전하게 암호화할 수 있을 뿐만 아니라
피싱사이트인지 아닌지 구분할 수도 있다.

HTTPS 프로토콜은 SSL(보안 소켓 계층)을 사용함으로써 이 문제를 해결했다. SSL은 서버와 브라우저 사이에 안전하게 암호화된 연결을 만들 수 있게 도와주고 서버 브라우저가 민감한 정보를 주고받을 때 이것이 도난당하는 것을 막아준다.
<br/>
<br/>

## Big diffrence between HTTP and HTTPS 
### SSL
<br/>
<img src="https://seopressor.com/wp-content/uploads/2017/07/Difference-Between-HTTP-and-HTTPS.png" width= 100%/>
<br/>
<br/>
<br/>

두 프로토콜 사이에 가장 커다란 차이점은 바로 SSL 인증서이다. HTTPS는 쉽게 말하여 HTTP 프로토콜에 보안기능을 추가한 것이라고 할 수 있지만 보안 기능은 생각보다 매우 중요하다. 특히 신용카드 정보나 비밀번호등 사용자들의 민감한 정보들을 다루는 웹 사이트라면 더욱 그렇다.

SSL 인증서는 사용자가 사이트에 제공하는 정보를 암호화하는데, 즉 **데이터를 암호로 바꾼다**고 생각하면 쉽다.

이렇게 암호화되어 전송된 데이터는 중간에서 누군가 훔쳐 낸다고 하더라도, 데이터가 이미 암호화되어 있기 때문에 해독할 수 없다.



#출처
(https://velog.io/@mactto3487/HTTP%EC%99%80-HTTPS%EC%9D%98-%EC%B0%A8%EC%9D%B4)
(https://brunch.co.kr/@hyoi0303/10)
(https://kimmy100b.github.io/tech/2020/03/07/http-https/)
(https://hyeran-story.tistory.com/159)
