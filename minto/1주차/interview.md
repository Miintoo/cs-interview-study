## 변수란 무엇인가?

변수는 하나의 값을 저장하기 위해 확보된 메모리 공간 자체를 의미한다.

## 식별자란 무엇인가?

메모리에 존재하는 공간을 식별하는 모든 값을 식별자라고 한다.

즉 변수는 메모리 공간이고 식별자는 해당 변수의 이름을 의미한다.

## 변수를 선언한다는 것은 어떤 것을 의미하나요?

변수를 사용하려면 변수의 선언은 필수이다.

메모리 상에 특정 공간을 확보하고 식별자에 해당 메모리 공간의 주소값을 맵핑하는 과정을 의미한다.

## var 키워드는 뭔가요?

변수를 선언하는 동작이 수행되는 약속된 자바스크립트 명령어이다.
변수가 선언되고 자동으로 undefined 값이 할당이 되는 독특한 특징이 있다.

## var 키워드의 문제점은 무엇이 있나요?

첫번째는 var 키워드는 재선언이 가능하다. 기존에 사용하던 변수명을 실수로 재 선언해서 사용하면 예상치못한 에러가 발생할 수 있다.

두번째는 호이스팅 문제이다. var의 경우에는 선언과 초기화가 동시에 진행이 된다. 그리고 이 과정은 런타임 환경전에 미리 수행이 되기 때문에 var 선언줄전에도 해당 변수를 참조할 수 있다.

세번째는 스코프 문제이다.
함수나 블록 스코프 내부에서 var로 선언된 변수는 블록 밖에서도 참조가 가능하다.
이로인해 코드를 작성하는 중간에도 작성한대로 동작하지 못한다는 불안감이 생길 수 있다.

## let 키워드는 var 키워드와 어떤 점이 다른가요?

첫번째는 재선언의 유무이다.
let은 재선언이 불가능하고 var은 재선언이 가능하다.

두번째는 호이스팅이다.
정확히는 변수는 선언 > 초기화 > 할당 3가지 단계로 이루어지는데 var은 선언과 동시에 선언과 초기화 단계가 수행이 되고 let은 선언단계만 진행이 되고 런타임 환경에서 해당 줄에 도달했을때 초기화와 할당 단계가 이루어진다. let에서 선언과 초기화 단계의 시간의 간극을 TDZ라고 한다.

세번째는 스코프의 차이이다.
var은 선언되면 전역 스코프에 저장이 되어 블록 안에서 선언해도 전역환경에서 접근이 가능하지만 let같은 경우에는 스코프에 변수가 저장 되기 때문에 외부에서 참조가 불가능하다.

## const 키워드는 어떤 특징이 있나요?

const는 선언과 할당을 동시에 해줘야한다. 그리고 한번 할당한 값을 재할당 하는게 불가능하다.
