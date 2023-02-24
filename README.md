## 안녕하세요👋🏻

웹 스터디를 시작하겠습니다.

<hr>

### 목차

1. [html, css, js가 웹 개발에서 어떤 부분을 차지할까](#html,-css,-js가-웹-개발에서-어떤-부분을-차지할까)
2. [react와 같은 프레임워크가 등장한 이유](#react와-같은-프레임워크가-등장한-이유)
3. [react 기본](#react-기본)
4. [간단하게 계산기 프로그램 만들어보기](#간단하게-계산기-프로그램-만들어보기)
5. [css 기본과 종류](#css-기본과-종류)
6. [마무리](#마무리)

<hr>

## html, css, js가 웹 개발에서 어떤 부분을 차지할까

`html`, `css`, `js`를 다들 한 번씩은 들어보셨을거라 생각합니다.

<center><img width="394" alt="스크린샷 2023-02-24 오후 11 04 48" src="https://user-images.githubusercontent.com/72312559/221198123-724a5585-c809-4ab0-9c87-e74539d78b88.png"></center>
<br>

**`HTML(Hypertext Markup Language)`은 말 그대로 마크업 언어입니다.**
[html mdn 문서](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/Getting_started)

- 예로 디자이너가 레이아웃이 구성된 부분을 주면 기능을 제외하고 레이아웃만 구성한다고 생각하시면 됩니다.

**`CSS(Cascading Style Sheets)`는 위에 html로 구성한 부분에 스타일을 적용하는 코드입니다.**
[css mdn 문서](https://developer.mozilla.org/ko/docs/Learn/Getting_started_with_the_web/CSS_basics)

- 다들 아실거라 생각!

**`JS(Javascript)`는 위에서 구성한 것들에 기능을 넣어주는 코드라 생각하시면 됩니다.**
[js mdn 문서](https://developer.mozilla.org/ko/docs/Web/JavaScript)

- 각종 이벤트를 적용하려 작성하는 코드고 이 부분이 `프론트엔드 개발자의 역량`입니다.

옛날에 `개발을 편하게 해주는 프레임워크, 라이브러리`들이 등장하기 전엔 위 세개를 사용해 개발을 진행했는데요.
특히 vanila js(순수 js)만을 사용해 개발을 하는 건 웹 개발자 입장에서도 아주 피곤한 일이었습니다.
간단한 기능에도 작성해야하는 코드도 방대하고, 직접 DOM(html에 작성한 태그)에 접근해야한다는 점도 버그를 일으키기 좋은 환경이기도 했기 때문입니다.

이러한 부분을 개선하기위해 개발자들은 더 편리한 프레임워크, 라이브러리들을 개발하기 시작했고, `jQuery`, `ejs`, `pug`와 같은 라이브러리, 템플릿 언어들이 나오기 시작했습니다. 그땐 혁신적이었지만, 현재는 **react가 전세계 웹 시장을 지배**하고 있고, 앞으로 몇 년간은 끄떡없을 거라 생각해 저희는 react를 사용해 웹 스터디를 진행합니다!

<hr>

## react와 같은 프레임워크가 등장한 이유

<center><img width="394" alt="스크린샷 2023-02-24 오후 11 05 48" src="https://user-images.githubusercontent.com/72312559/221198320-f2558e75-d2d7-49f7-8c15-60fe8ea3f385.png"></center>
<br>
react는 정말 혁신적인 프레임워크입니다. `순수 js`와 `react`로 작성한 카운터 프로그램을 통해 비교해보겠습니다.
아래는 순수 js를 이용한 간단한 카운터를 구현하는 방법입니다.

**html**

```html
<html>
  <head>
    <meta charset="UTF-8">
    <title>counter</title>
  </head>
  <body>
    <h1 id="number">0</h1>
    <div>
      <button id="increase">up</button>>
      <button id="decrease">down</button>
    <div>
    <script src="js 경로"><script>
  </body>
</html>
```

**js**

```js
const number = document.getElementById("number");
const increase = document.getElementById("increase");
const decrease = document.getElementById("decrease");

increase.onclick = () => {
  const current = parseInt(number.innerText, 10);
  number.innerText = current + 1;
};

decrease.onclick = () => {
  const current = parseInt(number.innerText, 10);
  number.innerText = current - 1;
};
```

직접 getElementById를 통해 DOM에 접근하는 모습! html, js를 따로 파일을 둬서 작성해야하는 모습!
저 DOM을 찾기위해 성능을 얼마나 소진하고 개발자는 이것저것 찾아다니느라 유지보수하기 얼마나 힘들지 정말 소름돋네요...

다음은 React를 사용한 카운터입니다.

```jsx
import React from 'react';

const counter = () => {
  const [count, setCount] = React.useState(0);

  return (
    <h1>{count}</h1>
    <div>
      <button onClick={setCount(() => prev + 1)}>up</button>
      <button onClick={setCount(() => prev - 1)}>down</button>
    <div>
  )
}
```

위 순수 js로 작성한 코드보다 훨씬 간결하고 명확하다는 건 코드를 모르고 봐도 대충 이해가 될거라 생각합니다.
이 뿐만 아니라 다양한 기능을 지원해줍니다! 이 부분은 다음 챕터에서 배워보도록 하겠습니다.

<hr>

## react 기본

저는 공식문서를 애용하는 입장으로써 이 부분은 공식문서로 1차로 터득하신 후 배우시면 훨씬 좋을 것 같다는 생각이 듭니다!
다만, 이전 legacy인 class형 react는 이번 스터디에서 다룰 부분이 아닙니다.

[react hook 공식문서 링크](https://ko.reactjs.org/docs/hooks-intro.html)

위 링크를 대충 훑어보고 이 부분부터 읽으시면 좋을 것 같아요. 간략하게 설명드리면 `class형 컴포넌트는 이전 레거시`이며, 생명주기도 복잡하고 유지보수 측면에서 단점이 많고 최신 라이브러리들은 지원하지 않는 경우가 많아 대부분 `함수형 컴포넌트인 hook`을 사용합니다.
(LEVEL 리팩토링 작업이 class => hook 전환...)

#### useState

useState는 흔히 react에서 얘기하는 `상태관리에서의 상태`입니다(변수 라고도 합니다). 이 부분을 잘 관리하면 프로그램, 코드 품질이 올라가 유지보수하기 쉽겠죠? 그래서 어떤 상태를 정의할 때 이게 정말 필요한 상태일까 항상 생각하며 코드를 작성하면 좋을 것 같습니다.

```jsx
import React, { useState } from "react";

function App() {
  // 새로운 state 변수를 선언하고, count라 부르겠습니다.
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

위에서 작성한 코드도 이 부분에 있네요!

```jsx
const [count, setCount] = useState(0);
```

변수를 선언하는 부분입니다. 각 컴포넌트에 사용하는 변수들을 선언할 수 있습니다.
react에서 제공하는 `useState`를 사용하면 `count라는 값`과 `setCount라는 함수`를 제공해줍니다.
`setCount`를 사용해 특정 이벤트일 때 count값을 바꿔줄 수 있다고 생각하시면 될 것 같습니다.

```jsx
return (
  <div>
    <p>You clicked {count} times</p>
    <button onClick={() => setCount(count + 1)}>Click me</button>
  </div>
);
```

위에서 선언한 값과 함수를 컴포넌트 내부에서 사용하는 모습입니다. 버튼을 클릭했을 때 setter함수를 이용해 count를 1씩 늘리고 있네요!

```jsx
import React, { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  const handleCountUp = () => {
    setCount(() => count + 1);
  };

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={handleCountUp}>Click me</button>
    </div>
  );
}
```

저는 요소 내부에 위처럼 명확하게 함수명이 들어가 있는 걸 좋아합니다! 다들 코딩하며 본인만의 스타일을 정의해도 좋을 것 같아요.

#### useEffect

javascript는 비동기 싱글쓰레드 언어입니다. 비동기란 순서대로 진행되지 않는다고 생각하시면 될 것 같아요.

멀티쓰레드인 타언어에 비해 싱글쓰레드 언어는 성능 개선이 아주아주 중요합니다.(멀티는 여러개가 각자 작업을 잡지만 싱글은 혼자 다 처리해야됨)
그래서 동기적으로 작성되는 타 언어와 다르게 js는 비동기적으로 작동합니다.
이 비동기, 동기 처리 부분이 오류도 많이 발생시키고 처리하기 번거로워 js개발자들의 고충이 많이 담겨있습니다.

```js
console.log("1");
console.log("2");
console.log("3");
```

예로 위는 순서대로 호출이 되지만,

```js
console.log("1");

setTimeout(() => {
  console.log("2");
}, 1000);

console.log("3");
```

은 순서대로 호출이 안 됩니다. 예로 setTimeout이라는 1초 뒤에 호출되는 함수를 작성했는데, 실제 코드에선 성능을 위해 setTimeout으로 정의한 값이 아니라도 늦게 호출되는 경우가 있어 예시로 들어봤습니다.

그래서 react에서도 비동기 처리를 위한 기능들을 지원해주는데요.

```jsx
import React, { useState } from "react";

export function App() {
  const [count, setCount] = useState(0);

  const handleCountUp = () => {
    setCount(() => count + 1);

    console.log(count); // ??
  };

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={handleCountUp}>Click me</button>
    </div>
  );
}
```

위 handleCountUp 함수에서 setCount로 1을 늘리고 count를 호출합니다.

만약 첫 번째 눌렀을 때 1이 나올까요? 정답은 땡입니다.
[react 코드 실행할 수 있는 링크](https://playcode.io/react)
위 링크에서 위 코드를 복사해서 진행해보세요!

이게 바로 비동기 동기의 차이인데요. 저희는 당연히 count가 올라갔고, count를 호출해 1이 나올 줄 알았지만 어림도 없었습니다.

위는 `useEffect`를 사용해 쉽게 해결할 수 있습니다.
useEffect는 컴포넌트 내부에서 바뀌는 의존값에 따라 특정 함수 및 코드를 실행시켜 준다고 생각하시면 편할 것 같아요.

```jsx
import React, { useState, useEffect } from "react";

export function App() {
  const [count, setCount] = useState(0);

  const handleCountUp = () => {
    setCount(() => count + 1);
  };

  useEffect(() => {
    console.log(count);
  }, [count]);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={handleCountUp}>Click me</button>
    </div>
  );
}
```

위 코드를 실행해보면 이제 값이 정상적으로 동작하는 걸 알 수 있습니다.

```jsx
useEffect(() => {
  console.log(count);
}, [count]);
```

첫 실행, count가 바뀔때마다 console.log(count)를 실행한다는 의미입니다.

```jsx
useEffect(() => {
  console.log(count);
}, []);
```

useEffect의 두 번째 인자인 dependency 배열이 빈 값이면 해당 컴포넌트가 처음 마운트될 때만 실행된다고 생각하시면 될 것 같아요.
useEffect도 여러번 호출할 수 있으니 관심사를 분리해 잘 호출해야 프로그램이 정상적으로 동작될거에요!

이 정도 배웠으면 간단한 프로그램을 만드는데는 문제가 없을거에요.

이제 간단하게 계산기 프로그램을 만들어볼까요?

## 간단하게 계산기 프로그램 만들어보기

[react 코드 실행할 수 있는 링크](https://playcode.io/react)

해당 링크에서 작성해보세요! vscode, git 사용법은 추후 프로젝트를 진행할 때 알려드리겠습니다.

```
프로그램 요구사항

1. 더하기, 빼기, 곱하기, 나누기가 가능한 계산기 프로그램이면 좋겠습니다.
2. 초기화 버튼이 있었으면 좋겠습니다.
3. 계산기 이벤트가 동작할 때 input값이 초기화되었으면 좋겠습니다.
```

먼저 위에 공식문서 및 useState, useEffect 글을 읽었으면 충분히 개발 가능할거라 생각이 듭니다.
위 링크를 들어가면 기본 코드가 아래처럼 되어있을텐데, 저희에 맞게 수정하겠습니다.

```jsx
import React from "react";

export function App(props) {
  return (
    <div className="App">
      <h1>Hello React.</h1>
      <h2>Start editing to see some magic happen!</h2>
    </div>
  );
}

// Log to console
console.log("Hello console");
```

이걸

```jsx
import React, { useState, useEffect } from "react";

export function App(props) {
  const [value, setValue] = useState(0);
  const [result, setResult] = useState(0);

  const onChange = (e) => {
    // input값 바꿀 때마다 value에 값 최신화
    setValue(+e.target.value);
  };

  return (
    <div>
      <span>{value}</span>
      <input onChange={onChange} value={value} />
      <h1>result: {result}</h1>
      <div>
        <button>+</button>
        <button>-</button>
        <button>x</button>
        <button>/</button>
        <button>reset</button>
      </div>
    </div>
  );
}
```

위와 같이 바꿔주세요! input에 바뀐 값에 대한 건 구현해놨습니다. 각 버튼별로 `value`, `result 상태`를 관리해보세요!

위에서 배운 useState, useEffect를 사용해 구현해보세요.
js를 모르시는 분들이 위를 구현하기 위해 필요한 문법을 아래 정리해드릴게요!

##### 함수 선언

```js
// 함수 선언 방법 1
function add(a, b) {
  return a + b;
}

// 함수 선언 방법 2
const add = (a, b) => {
  return a + b;
};

// 함수가 바로 return할 때
const add = (a, b) => a + b;
```

##### 버튼에 이벤트 주는 방법

```jsx
// button에 onClick event 주는 법 (함수에 넘겨줘야하는 값이 없을 때)
<button onClick={함수}></button>

// 함수에 값을 받아야 한다면 (위 add함수에 a,b를 넘겨줘야 되는 상황이면)
<button onClick={() => 함수(a, b)}></button>
```

##### +, -, x, / 방법

```js
const a = 1 + 2; // +
const b = 1 - 2; // -
const c = 1 * 2; // x
const d = 1 / 2; // /
```

예시로 **+ 를** 구현해보면 (🔥 처음엔 안 보고 구현하는 걸 추천드립니다)

```jsx
import React, { useState, useEffect } from "react";

export function App(props) {
  const [value, setValue] = useState(0);
  const [result, setResult] = useState(0);

  const addition = (value) => {
    setResult(result + value);
  };

  const onChange = (e) => {
    setValue(e.target.value);
  };

  return (
    <div>
      <span>value</span>
      <input onChange={onChange} value={value} />
      <h1>result: {result}</h1>
      <div>
        <button onClick={() => addition(value)}>+</button>
        <button>-</button>
        <button>x</button>
        <button>/</button>
        <button>reset</button>
      </div>
    </div>
  );
}
```

위처럼 구현하면 되겠죠??

나머지도 충분히 구현할 수 있을거라 생각합니다. (필요한 문법이 위에 다 있어요!)

완성된 코드는

```jsx
import React, { useState, useEffect } from "react";

export function App(props) {
  const [value, setValue] = useState(0);
  const [result, setResult] = useState(0);

  const onChange = (e) => {
    setValue(+e.target.value);
  };

  const addition = (value) => {
    setResult(result + value);
  };

  const subtraction = (value) => {
    setResult(result - value);
  };

  const multiplication = (value) => {
    setResult(result * value);
  };

  const division = (value) => {
    setResult(result / value);
  };

  const reset = () => {
    setResult(0);
  };

  return (
    <div>
      <span>value</span>
      <input onChange={onChange} value={value} />
      <h1>result: {result}</h1>
      <div>
        <button onClick={() => addition(value)}>+</button>
        <button onClick={() => subtraction(value)}>-</button>
        <button onClick={() => multiplication(value)}>x</button>
        <button onClick={() => division(value)}>/</button>
        <button onClick={reset}>reset</button>
      </div>
    </div>
  );
}
```

위와 같습니다. 그러나 다른 계산기처럼 `+`, `-`, `x`, `/` 이벤트마다 input이 초기화되면 좋겠다는 요구사항이 있으니 구현해볼까요?
이 부분은 공통으로 쓰이는 거니 공통함수로 구분하면 좋을 것 같네요!

```jsx
const resetValue = () => {
  setValue(0);
};
```

또한 `result가 바뀔때마다` 선언이 되는 거니`useEffect`를 사용하면 좋겠죠?

```jsx
import React, { useState, useEffect } from "react";

export function App(props) {
  const [value, setValue] = useState(0);
  const [result, setResult] = useState(0);

  const onChange = (e) => {
    setValue(+e.target.value);
  };

  const resetValue = () => {
    setValue(0);
  };

  const addition = (value) => {
    setResult(result + value);
  };

  const subtraction = (value) => {
    setResult(result - value);
  };

  const multiplication = (value) => {
    setResult(result * value);
  };

  const division = (value) => {
    setResult(result / value);
  };

  const reset = () => {
    setResult(0);
  };

  useEffect(() => {
    resetValue();
  }, [result]);

  return (
    <div>
      <span>value</span>
      <input onChange={onChange} value={value} />
      <h1>result: {result}</h1>
      <button onClick={() => addition(value)}>+</button>
      <button onClick={() => subtraction(value)}>-</button>
      <button onClick={() => multiplication(value)}>x</button>
      <button onClick={() => division(value)}>/</button>
      <button onClick={reset}>reset</button>
    </div>
  );
}
```

react의 정말 기초적인 문법으로 정상적으로 동작하는 간단한 계산기를 만들었습니다!
이제 다음 목차에서 해당 계산기를 꾸며보도록할까요?

## css 기본과 종류

css또한 사용성에 맞게 계속 변화하고 라이브러리도 많이 생기고 있습니다.
기본적으로 DOM에 접근해서 스타일링을 하는 모던한 방식이 있고,
css파일 없이 js파일 내부에서 정의해서 사용하는 css in js 방식이 있습니다.

저희 구름은 공통적으로 scss방식을 사용해요. css파일이 따로 있으며,
DOM에 접근해서 스타일링을 합니다.

그러나 요즘 유행하는 css방식은 css in js입니다.
토스에서는 emotion을 사용하고, 카카오페이에서는 styled component를 사용하고 등등..

이건 스타일의 차이입니다! 개발자로선 뭐가 더 좋고 이런건 없는 것 같아요.
금방금방 배울 수 있는 부분인 것도 큰 것 같아요.

저희는 css 방식은 전적으로 `jack`의 의견을 따르겠습니다! css애 관심이 많아 신청해주셨으니 사용하고 싶은 라이브러리 사용하시면 될 것 같아요.

실무에서 자주 쓰이는 css 기능은

```css
.font {
  color: red; /* 글씨 color 지정 */
  background-color: black; /* 배경 색 지정 */
}

.layout {
  display: flex; /* flex 기법 */
  display: grid; /* flex 기법 */

  margin: 16px; /* margin */
  padding: 16px; /* padding */

  border: 1px solid gray; /* border */
  border-radius: 8px; /* border radius */
}

.position {
  position: absolute; /* position 지정 */
}
```

등등이 있겠네요. css는 금방금방 배울 수 있고 잘 찾아보면 좋은 자료들이 참 많습니다.
그 중에서 가장 헷갈려 하는 게 display flex인데요.

[flex 1타 블로그](https://studiomeal.com/archives/197)
이거 한 번 읽어보시면 이해하기 정말 쉽습니다. (1분 코딩 만세)

앞에서 만든 계산기를 꾸며볼까요??

옆에 src를 보면 style.css가 존재하네요.

<img width="1114" alt="스크린샷 2023-02-24 오후 10 48 55" src="https://user-images.githubusercontent.com/72312559/221194664-9e447901-5b4e-4634-a3b3-f6763965cbca.png">

아래 사진과 같이 className을 적용하고
<img width="1040" alt="스크린샷 2023-02-24 오후 10 53 29" src="https://user-images.githubusercontent.com/72312559/221195562-d6576682-41aa-4293-837e-74097aefee26.png">

.className 형식으로 style을 하시면 됩니다.
<img width="1040" alt="스크린샷 2023-02-24 오후 10 53 34" src="https://user-images.githubusercontent.com/72312559/221195577-590d3742-132c-412c-9377-9d741ab270c8.png">

추후 다룰 css는 `jack`께서 원하시는 방식으로 다뤄보도록 하겠습니다.

## 마무리

네... 누군가에겐 엄청 쉬웠을거고, 누군가에겐 어려울 수 있을 것 같습니다🥲
디자이너분들이든, 알고리즘 크리에이터분들이든 잘 따라오시면 나중에 프로젝트 같이 하면 재밌을 것 같아요!
다음엔 리액트 원리(동작원리, 서버통신 원리) 및 심화(hook), 시멘틱한 웹 주제로 다뤄보려고 합니다!
아마 이번에 useState, useEffect를 잘 숙지하셨으면 따라오는덴 전혀 문제가 없을거에요.
js문법이 아마 가장 문제인데, 이 부분은 위에 js mdn 문서 참고하시면서 배워가는 것도 좋을 것 같습니다.
다들 고생하셨습니다~!
피드백 주시면 반영하겠습니다!
[스터디 노션 링크](https://www.notion.so/goorm/Web-Develop-Study-af0ebfe5264947a287ef7ca01b0a9504?pvs=4)
