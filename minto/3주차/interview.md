## CSR, SSR, SSG 렌더링 과정에 대해서 설명해주세요.

#### 1. CSR

CSR는 클라이언트로 부터 요청을 받으면 서버는 html과 js를 내려준다. 그럼 브라우저에서
서버로 부터 받은 데이터를 기준으로 렌더링을 진행해서 사용자에게 페이지를 보여주는 방식이다.

#### 2. SSG

SSG는 미리 서버에서 페이지를 만들어둔다. 그래서 클라이언트에서 요청이 오면 미리 만들어놓은 페이지를 응답하고 브라우저는 추가적인 렌더링없이 받은 페이지를 보여주기만 하면 된다.

초기 TTV가 굉장히 빠르고 SEO에 좋지만 사용자별로 다른 페이지를 보여주는 동적 페이지 렌더링은 하지 못한다.

#### 3. SSR

SSR은 클라이언트에서 요청이 들어왔을 때 서버에서 페이지를 렌더링해서 클라이언트에게 응답하는 방식이다.
SSG하고 비슷하지만 서버에서 요청마다 동적으로 페이지를 렌더링 한다는 점에 차이가 있다.

## 브라우저의 렌더링 과정

HTML이 처음으로 응답을 받아 DOM트리를 렌더링 한다. 그리고 CSS 코드를 만나게 되면 새로운 CSS를 요청해 받아와 CSSOM 트리를 렌더링 하게 된다.

## 브라우저의 css 선택자 선택 방법과 성능 차이

브라우저에서 css 선택자는 6가지가 있다.
태그를 이용해서 선택하는 선택자, id 선택자, 클래스 선택자, 속성 선택자, 가상 클래스 선택자, 가상 요소 선택자로 구성되어있다.

조금 더 구체적인 선택자일수록 성능에 유리하다. 왜냐하면 선택자 범위가 넓으면 모든 하위 요소에서 많은 작업을 수행하기 때문이다.

## script 태그에서 async와 defer의 차이~

async와 defer 둘다 병렬로 js를 불러오는 명령어이다.
하지만 js를 렌더링 하는데 순서가 다르다. async의 경우에는 js의 다운이 완료되면 html 파싱이 끝나기를 기다리지 않고 바로 실행이 되고 defer의 경우에는 js를 병렬적으로 다운 받지만 html의 파싱이 모두 끝나기를 기다렸다가 수행이 된다는 차이가 존재한다.

## 프로세스와 스레드란?

프로세스는 컴퓨터에서 동작하고 있는 프로그램을 의미한다. 스레드는 하나의 프로세스에서 동작하고 있는 하나의 작업 단위를 의미한다. 그래서 하나의 프로세스에서는 최소 하나의 스레드가 존재하고 여러 스레드가 존재할 수 있다.

## 싱글 스레드와 멀티 스레드란?

싱글 스레드는 하나의 프로세스에서 하나의 스레드 단위로만 동작을 처리하는걸 의미한다.
하나의 스레드로 모든 동작이 처리 되니깐 하나의 자원을 순차적으로 처리하면 돼서 직관적이고 쉽다. 하지만 하나의 작업에 문제가 발생하면 전체 프로세스의 동작에 영향을 미치는 단점도 존재한다.

멀티 스레드는 하나의 프로세스에서 여러 스레드가 병렬적으로 작업을 하는걸 의미한다.
각각의 스레드가 한정된 자원을 활용하기 때문에 메모리의 동기화 작업이 별도로 필요하지만 하나의 작업이 문제가 있어도 전체 프로세스에게 영향이 가지는 않을 수 있다.

## 버츄얼 돔과 리얼 돔의 차이를 설명해주세요.

리얼돔은 브라우저상에 실제로 렌더링 되는 돔을 의미한다.
버츄얼 돔은 리얼돔을 복사본이다. 그래서 버츄얼돔을 이용해서 변경점이 있는 부분을 바꿔주고 최종본과 기존 리얼돔과의 차이점을 분석해 바뀐 부분만 다시 렌더링을 해주는 방식으로 성능을 최적화할 수 있다.

## useRef란?

리액트에서 사용하는 hook이다. 리액트에서 useRef를 통해 상태를 저장했을때는 해당 상태값이 변경이 되어도 화면의 렌더링이 발생하지 않는다.

### hook이란 뭔데?

리액트의 다양한 기능을 제공해주는 함수를 의미한다.

#### 다양한 기능에는 어떤게 있는데?

상태를 관리해주는 useState나 컴포넌트가 마운트 돼었을때 콜백이 호출되도록 해주는 useEffect등이 있다.

## closure 란?

클로저는 함수가 선언될 당시의 환경을 기억해 함수의 호출이 끝나도 해당 변수 및 객체를 참조할 수 있는 특성을 의미한다.

### 그럼 closure는 언제 사용돼?

클로져를 이용해서 모듈 패턴이나 캡슐화, 비동기 작업 메모이제이션의 작업이 가능하다.

## Async/Await와 Promise의 차이점은?

promise에 chaining 문법으로 작성하기 보다 async/await 문법은 동기적으로 보이도록 작성이 가능해 가독성에도 좋고
try catch 문으로 에러를 헨들링 하는 부분도 가독성이나 유지보수 측면에서 더 좋다.

## HTTPS란?

기존 HTTP 프로토콜에서 Secure 보안이 추가된 프로토콜이다. 해당 프로토콜의 내용이 탈취 당해도 암호화가 되어있기 때문에 보안적인 측면에서 더 업그레이드 되었다고 볼 수 있다.

참고로 크롬에 8버전 이후부터는 도메인 주소가 다른 경우 쿠키가 브라우저에 저장되지 않는 이슈가 있다. 이를 해결하기 위해서 SSL발급을 한 서비스만 쿠키 저장이 가능하다.

## TCP란 무엇인가?

기존 IP 방식으로 패킷을 통신하는 방식에서 TCP 통신을 통해 비연결성에 문제를 해결하고 데이터의 순서도 보장을 하면서 데이터의 신뢰성도 보장하기 위해서 적용된 기술이다.

3 way handshake 기술을 이용해서 통신을 할 주체끼리 신뢰성을 보장한 상태로 통신이 가능하도록 해준다.

## TCP와 UDP의 차이점은?

데이터 신뢰성에 차이가 존재한다.
UDP는 TCP처럼 3 way handshake 기법을 사용하지도 않기 때문에 통신 속도가 굉장히 빠르다.
이로 인해 실시간 스트리밍 같은 속도가 데이터의 신뢰성보다 더 중요한 경우 UDP 방식을 이용해 통신을 하기도 한다.

## 브라우저에서 URL을 입력시 어떤 일이 일어나는가?

URL 입력시 일단 DNS 캐시가 저장되어 있는 사이트가 아니라면 DNS 서버에 접속해 필요한 IP를 반환받는다. 그럼 IP주소를 통해 리소스가 있는 사이트로 HTTP 프로토콜을 이용해 접근을 하고 서버에서 사이트의 HTML 리소스를 응답 받는다. 그럼 브라우저는
응답 받은 HTML을 DOM 트리로 만들고 이 때 필요한 추가적인 CSS나 이미지 JS파일등의 리소스를 반환 받는다.
반환 받은 리소스에 CSS를 이용해서 CSSOM 트리를 렌더링하고 DOM트리와 CSSOM 트리를 이용하고 JS파일을 이용해 최종적인 렌더 트리를 만든다. 해당 렌더 트리를 이용해서 브라우저는 사용자가 보이는 웹 어플리케이션을 보여준다.

## JS Event Loop란?

자바스크립트의 런타임 모델이다. JS 내부에서는 비동기 처리나 동기 처리가 어떻게 이루어지고 있는지 확인할 수 있다.
구조로는 Call Stack과 Web API와 마이크로 테스크 큐와 테스크 큐로 이루어져 있다.
자바스크립트에서 수행되는 코드들은 모두 Call Stack으로 들어가게 되고 비동기적으로 수행이 되어야할 함수들은 모두 Call Stack에서 Web api로 옮겨서져서 비동기적으로 수행이 된다. 그리고 해당 함수의 실행이 끝나게 되면 마이크로 테스크큐와 테스크큐로 나누어서 콜백이 넘어간다. 그 상태에서 콜 스택에 모든 작업이 끝난 빈 상태가 되면 한번에 테스크 큐에 작업물들을 콜 스택으로 옮겨 함수의 작업을 수행한다.
이 작업을 이벤트 루프가 매우 빠른속도로 회전하면서 필요할 때마다 사용자에게 어색하게 보이지 않도록 해당 작업을 수행해준다.

## Restful API 란?

클라이언트와 서버간에 통신을 위한 규칙을 정의해 데이터를 전달하고 상태를 관리하는 방법을 정의한 개념이다.
