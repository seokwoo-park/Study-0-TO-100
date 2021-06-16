# Hoisting

## Definition of Hoisting
### (호이스팅의 정의)
<br/>

**함수 안에 있는 선언들을 모두 끌어올려서 해당 함수 유효 범위의 최상단에 선언하는 것을 말한다.**


JavaScript(자바스크립트)는 다른 언어와 다르다.

자바스크립트는 실행되기 전에 코드에 선언된 변수 및 함수를 코드 최상단으로 끌어와 선언한다.

하지만 **변수 범위가 전역 범위인지 함수 범위인지에 따라 다르게 수행된다.**
#
## REMEMBER!
<br/>

* 함수 내에서 선언한 함수 범위(Function scope)의 변수는, 해당 함수내의 최상위에 선언되며,
함수 밖에서 선언한 전역 범위(Global scope)의 전역 변수는 스크립트 단위의 최상위로 끌어올려진다.

* **변수의 선언과 할당 내용 모두를 상단으로 끌어올리는게 아니라, 선언부분만 분리하여 최상위로 끌어올린다.**
선언된 변수에 값을 할당하는 내용은 원래 위치에 있다.

* **최초 선언시 초기화한 경우에도, 선언과 할당으로 분리하여 호이스팅한다.**


## Examples
선언되지 않은 변수를 참조할 경우, 보통 아래와 같이 오류가 나타난다.
```javascript
console.log(a);	// Reference Error
```
하지만 아래의 예제에는 오류가 나타나지 않는다. 

```javascript
console.log(a);	// undefined

var a = 1;

console.log(a);	// 1
```
선언되지 않은 변수를 참조하는데 오류가 나지 않고 undefined로 값이 지정된 이유는 바로 Hoisting 때문이다. 위 코드의 실제 실행 과정은 대략 아래와 같이 실행된다고 볼 수 있다.
```javascript
var a;	// 변수 선언!부분만 끌어올려졌다.

console.log(a);	// undefined

a = 1;

console.log(a);	// 1
```
**Hoisting은 쉽게 생각하여 변수의 선언부분을 스코프 내 최상위로 끌어올린다고 생각하면 된다**
#
## Hoisting 의 대상

* 변수는 오로지 **var**의 변수선언 만 호이스팅이되며, **let / const 는 호이스팅이 발생하지 않는다.**
     ```javascript
    console.log(a);
     // let과 const는 a를 찾지 못하여 Error 발생
     // var 였다면 undefined 출력
    let a = 1;

    console.log(a);
    ```
* **함수 표현식(Function Expression)에서는 호이스팅이 발생하지 않는다.**
  
  > 함수표현식이란, 변수를 만들고 함수를 할당해주는 표현식이다.
    
    ```javascript
        a(); // TypeError : a is not a function

        var a = () => {
            console.log('It works!')
        }

    ```
    * 화살표 함수는 호이스팅이 불가능하다. 호출 시, 
    함수를 참조값 console.log(a)를 호출한 것이 아니라 함수를 출력 시켰다 a() 혹은 console.log(a()) 
    
    * console.log(a)를 호출했으면 예상한 대로 undefined가 출력되었을 것이다. 화살표함수의 a는 undefined가 되지만 함수로 초기화가 되지 않기 때문이다. 만약 a가 function a() 로 정의가 되었다면 함수로 초기화가 되면서 실행이 되었을 것이다.

* **함수선언식 (Function Declaration)에서는 정상적으로 호이스팅이 발생**
 > 함수 선언식으로 선언한 함수는 무조건 Hoisting이 되며 **함수 자체**가 hoisting이 된다.

```javascript
a();

function a () {
	console.log('It works!');
};

a();
```
위와 같이 작성하였을경우 아래와 같이 동작한다.

```javascript
function a () {
	console.log('It works!');
};

a();

a();
```

# Hoisting priority
## 호이스팅의 우선순위

* 같은 이름의 **변수** vs **함수** 
  * 변수 선언이 함수 선언보다 위로 끌어올려진다.


    ```javascript
    var a = 1;

    function a(){
        console.log('123');
    }

    console.log(a);	//1
    ```
* 값이 할당 되어있는 변수 vs 할당 되지않은 변수
  * 값이 할당되어 있지 않은 변수의 경우, 함수선언문이 변수를 덮어쓰지만 값이 할당되어 있는 변수의 경우, 변수가 함수선언문을 덮어쓰는 것을 볼 수 있다.
    ```javascript
    var a = 1;
    var b;

    function a() {
        console.log("123");
    }
    function b() {
        console.log("123");
    }

    console.log(a); // 1
    console.log(b); // function b
    ```

# Remember before Hoisting 
* 코드의 가독성과 유지보수를 위해 Hoisting이 일어나지 않도록 한다.
* Hoisting을 제대로 모르더라도 함수와 변수를 가급적 코드 상단부에서 선언하면, Hoisting으로 인한 스코프 꼬임 현상은 방지할 수 있다.
* let/const를 사용한다
#

#출처
(https://velog.io/@surim014/JavaScript%EC%97%90%EC%84%9C%EC%9D%98-Hoisting%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80)
(https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html)
(https://velog.io/@stampid/Hoisting%ED%98%B8%EC%9D%B4%EC%8A%A4%ED%8C%85%EC%9D%B4%EB%9E%80)




