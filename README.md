# :fire: Blog-Dev
***
### :blue_book: General
***
1. parameter vs argument
  - Parameter: variable listed as a part of the function definition
  ```js
  function varCheck(parameter1, parameter2){
    console.log(parameter1 + parameter2);
  }
  ```
  - Argument: values passed to the function when it is invoked(called)
  ```js
  varCheck(argument1, argument2);
  ```
2. CORS(Cross-origin-resource-sharing)
  - It allows AJAX requests to manage same origin policy
  - To put it simply, we need to use API datas
  - 보통 메인(client-side) 포트에서 다른 포트(server-side)에서 데이터를 요청의 실행을 위해쓰임
  - 
3. Babel
  - Javascript transpiler that converts ES6+ in to plain ES (Let browser understand the code)
  - Transpilates JSX
4. Webpack
  - Node module bundler that packaging assets
6. XMLHttpRequest
  - method that transfer data btw browser and server
  - Used for Ajax programming - retrieve data from URL w/o page refresh
7. Compiler vs interpreter
  - Compiler = Compiles instruction(program) in to machine code entirely - Faster but non-editable
  - Interpreter = Interprets instruction(program) in real time step by step - Slower but editable
8. HTML Tag usage - button element
  - Most of clickable thing in website uses either <a> or <button> elements.
  - why? for the following advantages SEO-friendly
  - 버튼 태그는 점점 쓰임새가 덜하는 이유가 default 스타일링 때문이다. - 이 부분은 reset 스타일을 하면 되긴함.
9. button 태그 스타일링 시 유의사함
  - button 스타일링 시 button Area 라는 parent 영역을 설정해주어야한다.
  ```css
    const buttonArea = {
      display: "flex",
      justifyContent: "center"
    };
    const button = {
      alignItems: "center",
      color: "white",
      backgroundColor: "tomato",
      borderColor: "tomato"
    };

  ```
10. DOM 에 관련하여..
  - DOM = HTML의 원하는 위치에 접근하여 Document 를 인식하고자 하는 방식
  - Vitrual DOM 을 사용하는 이유? = Automation of DOM fragment / SPA 에서는 DOM 조작이 많아지는데, 브라우저 연산이 많아짐 => 렌더링될 변화를 묶어서 진행
  - 추가 = VDOM은 추상화 / 가벼운 복사본을 만들고 변화의 전후 를 비교하여 업데이트한다. / 언제 DOM을 렌더링 할것인가? => 데이터가 변화했을때

11. CSS in advance = CSS preprocessor = SASS(SCSS) 
  - Why Sass? 기존의 Css 의 문제점
    - Maintainance & readability
    - Code redundancy & Difficulties in sturcturing
  - Traits of Sass
    - Advanced features and proactive community
  - Difference btw Sass and Scss
    - Scss is superset of Sass
    - CSS 거의 같은 문법으로 Sass 의 기능을 지원함.
    - Scss has {} and ; / @minxin and @include
  - How preprocessor compiles Sass?
    - 웹에서는 결국 표준 css 로 처리해야함
    - Under node.js development env, following options:
      - SassMeister, node-sass, gulp, webpack, parcel and etc
  - Sass vs Scss?
    - Sass: Concise & less strict syntax rules ( easy to read, easy to write )
    - Scss: Expressive & familiar syntax rules with css ( compatabile with css ) / supports multi line 
12. Bundler
  - :question: What is Bundler?
    - :exclamation: Bunlder is a tool that takes series of files and their dependencies into a single file.
    - :exclmation: 여러가지로 나누어져있는 파일을 하나의 파일로 만들어주는 도구이다.
  - :thinking: Why should we using it?
    - :open_mouth: HTTP Request 시에 소요되는 시간을 효율적으로 관리하기 위해
13. Cross-browsing
  - Enables to make web application which is client side features to work in differenct environments(browser)
  - 다양한 브라우저에서 동등한 기능을 제공하는 것이 주 목적이다.
  - 물론 디자인 측면이나 css 효과를 살려서 모든 브라우저에서 작동한다면 안성맞춤 이지만, 정작 중요한 웹사이트의 퍼포먼스를 깍아내리지 않는 선에서 조율.
14. Programming paradigm / 명령형 vs 선언형 
  - 명령형 (imperative, procedural) = 컴퓨터가 수행할 명령들을 나열, 순서대로 기재함 / How
    - 횡단보도까지 약 50m 이동 (영천로 55번길),
    - 횡단보도를 이용하여 GS슈퍼마켓 방면으로 횡단,
    - 횡단보도를 지나 약 120m이동
  - 선언형 (functional, logical ) = 목표와 수행할 task를 설명함 / What
    - 출발: 경기도 화성시 xx동 xxx로
    - 도착: 경기도 화성시 xx동 xxx로
  - is object oriented programming declarative or imperative?
    - 객체 지향형 언어인 C++, java 등은 명령형 프로그래밍을 지원하기위해 만들어졌다
15. Currying in detail
  - 함수형 프로그래밍 기법이며 함수를 재사용하는데 초점이 있다.
  - 여러가지의 params 를 받는 함수를 하나씩 분리하여 함수를 체이닝 하는 방법
  - 선언되어진 params 보다 적은 수가 들어온다면 분리해서 받는다 -> ? 지연처리가 가능하다
    - sum(3,4,5) -> sum(3)(4)(5)
  
  ```js
    function greet(greeting, name){
      console.log(greeting + ', ' + name);
    }
    
    function greet(greeting){
      return function(name){
        console.log(greeting + ', ' + name);
      }
    }
    
    var hello = greet("hello");
    hello("hogyun"); // hello, hogyun
    hello("john"); // hello, john
    
    var Hola = greet("Hola");
    Hola("hogyun"); // Hola, hogyun
    Hola("john"); // Hola, john
  ```

16. Strict vs lazy evaluation

### :green_apple: Node.js
***
1. Express
  - server side web application framework for node js

### :cyclone: React.js
***
1. Why are we using super in react?
  - We can not use 'this' keyword without declaring super in constructor.
  - Super calls 'React.Component' (in react)

2. What are components?
  - Simply, class or function that takes inputs(props) and returns React element
  
3. How React UI works?
  - Mounting -> Updating -> Unmounting
    - Mounting = 인스턴스가 생성되고 DOM에 나타나는 과정
      - Methods = constructor -> getDerivedStateFromProps -> render -> componentDidMount
        - constructor: Initialize state value / state 의 초기값 설정
        - getDerivedStateFromProps: props 와 state 값을 동기화 시킴
        - render: returns React elements
        - componentDidMount: 컴포넌트를 생성, 첫 렌더링후 호출되는 함수
        ```js
        import React, { Component } from 'react';

        class MyComponent extends Component{
            state = {
               number : 0
            }
            constructor(props)
            {
                super(props);
                console.log("Constructor Method 호출");
            }

            static getDerivedStateFromProps(nexProps, prevState)
            {
                console.log("getDerivedStateFromProps 호출");
                return null;
            }

            componentDidMount()
            {
                console.log("componentDidMount 호출");
            }

            render(){
                console.log("render 호출")
                return(
                    <div>
                        <h1>Hello World!! My Name is {this.props.name}</h1>
                    </div>
                )
            }
        }
        export default MyComponent;
        ```
    - Updating = props or state의 변경으로 컴포넌트가 re-render되는 과정 / 부모 컴포넌트가 리렌더링될떄, this.forceUpdate로 강제 re render
      - Methods = getDericedStateFromProps -> shouldComponentUpdate -> render -> getSnapShotBeforeUpdate -> componentDidUpdate
        - getDerivedStateFromProps: 마운트과정에서 이어짐 (?)- 업데이팅에서는 변화가 없나?
        - shouldComponentUpdate: 컴포넌트를 리렌더링할지 결정하는 함수. if returns true, it calls render,GSBU, CDU funcitons.
        - render: update 된 값을 가지고 re-render
        - getSnapshotBeforeUpdate: 변경된 요소를 DOM에 반영하기 직전에 호출됨
        - componentDidUpdate: 're'-render 이후에 호출되는 함수
        ```js
          import React, { Component } from 'react';

          class MyComponent extends Component{

              state = {
                  name : ""
              }

              constructor(props)
              {
                  super(props);
                  console.log("Constructor Method 호출");
              }

              static getDerivedStateFromProps(nextProps, prevState)
              {
                  console.log("getDerivedStateFromProps 호출");
              }

              shouldComponentUpdate(nextprops, nextState)
              {
                  console.log("sholudComponetUpdate 호출")
                  return true;
              }

              componentDidUpdate()
              {
                  console.log("componentDidUpdate 호출");
              }

              getSnapshotBeforeUpdate(prevProps, prevState)
              {
                  console.log("getSnapshotBeforeUpdate 호출")
                  return null;
              }

              handleOnChange = (e) => {
                  this.setState({
                      name : e.target.value
                  })
              }

              render(){
                  console.log("render 호출")
                  return(
                      <div>
                          <input onChange = {this.handleOnChange}></input>
                          <h1>Hello World!! My Name is {this.state.name}</h1>
                      </div>
                  )
              }
          }
          export default MyComponent;
        ```
  - React life cycle after 16.3
  ![react-life-cycel](https://github.com/hogyun3709/Blog-Dev/blob/master/blog-dev-docs/react-life-cycle.jpg)
  - When react components update
  ![react-update](https://github.com/hogyun3709/Blog-Dev/blob/master/blog-dev-docs/react-update.png)
  - React life cycle before 16.3
  ![react-ui-lifeCycle](https://github.com/hogyun3709/Blog-Dev/blob/master/blog-dev-docs/react-ui-lifeCycle.jpg)
  - Will hooks replace classes or redux
    - Hook 이 앞으로 걸어가야 할 리액트의 방향이긴 하나, Dan Abramov 는 기존의 앱을 훅으로 다시 사용 작성하라고는 권하지 않았다.
    - State Management 부분에서는 도움을 주는 것이 확실하니, 앞으로의 행보를 기대해봐야겠다.
    
  4. React v.17 updates
    - No new features, but improvements
    - Resources / Links 
      1. [React js Blog posts - Reactv17.0 release](https://reactjs.org/blog/2020/08/10/react-v17-rc.html)
      2. [The 6 major changes in react v17](https://medium.com/better-programming/the-6-major-changes-in-react-v17-0-d14fed5b0529)
      - React no longer suppoer event handlers at the document level (which means react handles eventss in Root elements)
      ![Event handlers comparsion v16 - v17](https://github.com/hogyun3709/Blog-Dev/blob/master/blog-dev-docs/event-handler-comparsion.png)
      - Changes in the following events
        - onScroll
        - onFocus, onBlur -> focusin, focusout
        - onClickCapture
      - No more Event Pooling (Optimization Failure)
      ```js
      function handleChange(e) {
        setData(data => ({
          ...data,
      // This crashes in React 16 and earlier:
         text: e.target.value
       }));
      }
      ```
   
   5. React state Management Library - Recoil
   - Resource Links below
      1. [Recoil - Another react state management library?](https://medium.com/swlh/recoil-another-react-state-management-library-97fc979a8d2b)
      2. [What is React Concurrent Mode?](https://medium.com/swlh/what-is-react-concurrent-mode-46989b5f15da)
    
   - Basically, Javascript is a single-threaded Language
   - React concurrent mode helps to execute almost 'multi-threaded' like mechanism
   - More detail, it helps to break tasks into pieces and run independetly
   - NOBA, the library expects a better user experiences
   
   6. State management - how to handle remote(fetch) data (api 데이터를 state 으로 관리해야하는 것인가에 대한 고찰) - using react hook only
   - Resource Link
      1. [Why you should be storing remote data in a cache - and not in state](https://medium.com/better-programming/why-you-should-be-separating-your-server-cache-from-your-ui-state-1585a9ae8336)
   - Issuing question: Wht is userData needs to be read from other components at different level of nesting?
      - Solution??: Context api, Mobx, Redux
      - :warning: Isn't it introduce an unnecessary layer of complexity? - need to repeat boilerplate
   - Remote data(Api data call) is read-only. It doesn't belong in the same location as our UI state.
   - Following two libraries help to manage remote data fetching - [SWR](https://github.com/vercel/swr), [react-query](https://github.com/tannerlinsley/react-query)
      
### :banana: Javascript
***
1. Require vs Import
  - Require: retrieve(call) modules(read packages) by using CommonJS
  ```js
  const hello = require('hello');
  const { world } = require('hello');
  ```
  - Import: retrieve(call) modules(read packages) by using ES6 feature
  ```js
  import hello from 'hello';
  import { world } = from 'hello';
  ```
2. Named Export(import) vs Default Export(import)
  - Named Export(import)
  ```js
  import { HomeComponent } from './HomeComponent';
  export const HomeConponent = () => {};
  ```
  - Default Export(import)
  ```js
  import HomeComponent from './HomeComponent';
  export default HomeComponent;
  ```
3. for ...in vs for ...of
  - for ...in = Access to object's keys / Any object
  ```js
  const obj = {
    a: 5,
    b: 6,
    c: 7
  }
  for (let keys in obj){
    console.log(keys); // a, b, c
  }
  for (let values in obj){
    console.log(obj[values]); // 5, 6, 7
  }
  ```
  - for ...of = Access to array's value / [Symbol iterator]
  ```js
  var iterable = [3, 5, 7];
  
  for(let key in iterable){
    console.log(key); // 0, 1, 2
  }
  
  for(let value of iterable){
    console.log(value); // 3, 5, 7
  }
  ```
4. Closure
  - Closure is the combination of a function. 흔히 함수 안의 함수라고도 한다.
  - It gives you access to an outer function's scope from an inner function. 내부 함수에서 외부 함수에 접근 할수있는 권한을 준다.
  - It creates surrounding state which is lecial environment. => Enables to build private function and variables.
  ```js
  function getClosure(){
   var greeting = 'Hello World';
    return () => {
      return greeting;
    }
   }
  var closure = getClosure();
  console.log(closure())
  ```

5. Hoisting
  - It is mechanism where var and fns declarations are moved to the top of their scope. 함수나 변수 선언 부분은 위로 끌어올린다. 대입은 그대로.
  - variable
  ```js
  function foo(){
    // var a; // has been declared
    console.log(a); // undefined
    var a = 100;
    console.log(a); // 100
  }
  ```
  - function
  ```js
  foo()  // Hello
  
  function foo(){
    console.log('Hello');
  }
  ````
  ```js
  foo(); // foo is not a function
  var foo = function(){
    console.log('Hello');
  }
  
  var foo;
  foo(); //foo is not a function
  foo = function(){
    console.log('Hello');
  }
  ```
6. AJAX - Asynchronous Javascript And XML
  - allows exchange data with web server behind the scene.
  - enables update/render part of the page without reloading the whole page
  
7. Function Scope vs Block Scope vs Lexical Scope
  - Function Scope: The area that variables exist in a funciton-scope accessibility.
  - Variable accessibilty only exists in the function.
  ```js
  function foo(){
    var fruit ='apple';
    console.log('inside function: ',fruit);
  }
  foo();                    //inside function: apple
  console.log(fruit);       //error: fruit is not defined 
  ```
  - Block Scope: The area with in conditional state and loops.
  - Const and let takes role of declaring variables in the block scope.
  ```js
  function foo(){
    if(true){
        var fruit1 = 'apple';        //exist in function scope
        const fruit2 = 'banana';     //exist in block scope
        let fruit3 = 'strawberry';   //exist in block scope

    }
    console.log(fruit1);
    console.log(fruit2);
    console.log(fruit3);
  }

  foo();
  //result:
  //apple
  //error: fruit2 is not defined
  //error: fruit3 is not defined
  ```
  - Lexical Scope: The area that children scope have the access to the variables defined in the parent scope.
  ```js
  var name = 'hogyun';
  function log() {
    console.log(name);
  }

  function wrapper() {
    var name = 'hugo'; //If not declaring, => name = 'hugo'; result will be hugo
    log();
  }
  wrapper(); // hogyun
  ```
8. IIFE(Immediately-invoked funciton expression)
  - Function that defines and returns simultaneously.
  - 초기화와, global scope varible 충돌 방지
  - 순수함수 프로그래밍에서 use case 가 있음.
  ```js
  (function() {
    var name = "hogyun"
    console.log(name)
  }())

  // hogyun
  ```
  ```js
  (function(score) {
    console.log(score)
  })(95)

  // 95
  ```
9. Iterable / Iterator protocool 
  - Array, Set, Map 등의 JS 내장 객체는 Iterable/Iterator protocool를 따른다.
  - Iterable: Iterator 리턴하는 [Symbol.iterator]() - 메소드 를 가진 값 - JS array 는 이터러블이다.
  - Iterator: { value, done } 으로 표현되는 Object 를 return 하는 next() - 를 가진 값
  ```js
  const arr = [1,2,3];
  arr[Symbol.iterator] // f values() { [native code] } = iterable
  arr[Symbol.iterator]().next(); // {value: 1, done: false} = iterator
  const iterator =  arr[Symbol.iterator(); // 이렇게 이터레이터로 만들어주어야 .next() 함수로 access 가능
  ```
10. Generator
  - It can stop midway and then continue from where it stopped.
  - It generates a value with the yield keyword rather than return
  - 이터러블을 생성하는 함수로도 여겨진다.
  - 이터레이터를 리턴하는 함수
  - async/await feature can be based on generator
  ```js
  function *gen(){
    yield 1;
    yield 2;
    yield 3;
  }
  
  let iter = gen();
  console.log(iter.next()); // { value: 1, done: false };
  console.log(iter.next()); // { value: 2, done: false };
  console.log(iter.next()); // { value: 3, done: false };
  console.log(iter.next()); // { value: undefined, done: true };
  ```
  ```js
  function *gen(){
    yield 1;
    yield 2;
    yield 3;
    return 100;
  }
  
  let iter = gen();
  console.log(iter.next()); // { value: 1, done: false };
  console.log(iter.next()); // { value: 2, done: false };
  console.log(iter.next()); // { value: 3, done: false };
  console.log(iter.next()); // { value: 100, done: true };
  
  for(const a of gen()) console.log(a); // 1 2 3 - 순회할땐 return 값은 없이 순회한다.
  ```
11. Callback
  - A function that is to be executed after another function has finsied.
  - Any function that is passed as an argument
  ```js
  /* sync callback */
  function greeting(name) { //greeting is callback function
  alert('Hello ' + name);
  }

  function processUserInput(callback) {
    var name = prompt('Please enter your name.');
    callback(name); // no need to have retrun statement 
  }

  processUserInput(greeting);
  ```
  - Generally using for handling async operation
  ```js
  /* Failure case */
  function findUser(id) {
    let user;
    setTimeout(function() {
      console.log("waited 0.1 sec.");
      user = {
        id: id,
        name: "User" + id,
        email: id + "@test.com"
      };
    }, 100);
    return user;
  }

  const user = findUser(1); // setTimeout 은 async 이기에 compiler pointer 는 이미 return user(undefined)를 할당된다.
  console.log("user:", user);
  /* result: 
   user: undefined
   waited 0.1 sec
  */
  ```
  ```js
  /* Successful case */
  function findUserAndCallBack(id, cb) {
    setTimeout(function() {
      console.log("waited 0.1 sec.");
      const user = {
        id: id,
        name: "User" + id,
        email: id + "@test.com"
      };
      cb(user);
    }, 100);
  }
  // 함수로 부터 결과값을 리턴 받기를 포기하고, 결과값을 이용해서 처리할 로직을 콜백 함수에 담아 인자(2번째) 로 던지면 된다.
  findUserAndCallBack(1, function(user) {
    console.log("user:", user);
  });
  /* result: 
  waited 0.1 sec
  user: {id: 1, name: "User1", email: "1@test.com"}
  */
  ```
12. Promise
  - Callback hell(비동기 프로그래밍시, 함수의 매개변수로 넘겨지는 콜백함수가 반복되는 현상)을 해결하기위한 패턴 중 하나
  - Callback vs Promise
  ```js
  function add10(a, callback){
    setTimeout(() => callback(a + 10), 1000);
  }
  add10(5, res => {
    add10(5, res => {
      add10(5, res => {
        console.log(res)
      }
    }
  }
  
  function add20(a){
    return new Promise(resolve => setTimeout(() => resolve(a + 20), 100));
  }
  add20(5)
    .then(add20)
    .then(add20)
    .then(console.log)
  ```
  - promise 는 보통 어떤 라이브러리의 함수를 호출하여 리턴받은 promise 객체를 사용하는 경우가 많다: fetch() 를 사용하여
  ```js
  function fetchAuthorName(postId) {
    return fetch(`https://jsonplaceholder.typicode.com/posts/${postId}`)
      .then(response => response.json())
      .then(post => post.userId)
      .then(userId => {
        return fetch(`https://jsonplaceholder.typicode.com/users/${userId}`)
          .then(response => response.json())
          .then(user => user.name);
      });
  }

  fetchAuthorName(1).then(name => console.log("name:", name));
  ```
  - 비동기 상황을 일급 값으로 다룬다. - return statement 가 있기 때문 - pending, fulfilled(resolved), reject
13. continue statement 
  - It terminates execution of statements in the current iteration of the current loop, and continues the next iteration
  - 컨디션에 부합하면, 해당하는 이터레이션을 멈추고 다음 이터레이션을 실행한다
  - break와 달리 루프의 실행을 완전히 종료하지않는다
  
14. API
  - Application programming interface
  - 소프트웨어 간의 지정된 형식으로 요청, 응답, 명령등을 받을 수 있게하는 수단
  
15. RESTful API
  - rest 하게 api를 디자인하는 방법을 말한다. 여기서 rest(restful)하게란?
  - 각 요청이 URI만으로도 어느정도 어떤 동작이나 정보를 위한 것인지를 추론 가능하게
  - GET, POST, PUT, DELETE, PATCH 와같은 5가지의 HTTP 요청으로 각각의 쓰임새에 일치 하게끔 어플리케이션을 디자인하는 것.
  - In advance
    - rest 한 제약 조건들의 집합

    
  * 참고자료
    - [RESR API가 뭔가요?](https://www.youtube.com/watch?v=iOueE9AXDQQ&fbclid=IwAR0uR8yXi97jX1gW3JtRh8tkiylFjEEJikhGLW-NRiY-mxf0m0NnTGQRjQs) (07:15)
    - [그런 REST API로 괜찮은가](https://www.youtube.com/watch?v=RP_f5dMoHFc) (47:02)
  
### :slot_machine: ML
***
1. Is Faster R-CNN best for object detection?<br>
- Overall topic: All about image classficatiion<br>
  - Reading articles about obj detection<br>
  -[Zero to Hero: Guide to Object Detection using Deep Learning: Faster R-CNN, YOLO, SSD](https://cv-tricks.com/object-detection/faster-r-cnn-yolo-ssd/)
  -[R-CNN, Fast R-CNN, Faster R-CNN, YOLO - Objecet Detectiion Alogirthms](https://towardsdatascience.com/r-cnn-fast-r-cnn-faster-r-cnn-yolo-object-detection-algorithms-36d53571365e)

2. 
### :ledger:HTML/CSS
***
1. CSS - UNITs :) / CSS에서 사용하는 여러가지의 단위
###### Absolute: 사용자 / 브라우저의 설정 & 변화로 접근성 문제를 유발 할수 있음
  - px, pt, cm, in
###### Relative
  - em, rem, cap, ch, ex, ic, lh, rlh
  - 보통 em과 rem 은 확대 가능한 레이아웃을 만들기 위해 쓴다 / 예를 들어 그리드 시스템?
  - em 과 rem은 css 의 font-size 속성값에 비례 하는 상대단위
    - EX) font-size: 16px:
      - 0.5em = 16px x 0.5 = 8px
      - 1em = 16 px x 1 = 16px
      - 2em = 16 px x 2 = 32px
    - EX) font-size: 20px;
      - 0.5em = 20px x 0.5 = 10px
      - 1em = 20px x 1 = 20px
      - 2em = 20px x 2 = 40px
  - em 과 rem 의 차이 ? 'r' = root, rem 은 최상위 요소의 속성값에 비례, em 은 해당하는 요소/태그
  - Viewport % lengths
    - vh, vw, vi, vb, vmin, vmax
    - vh와 vw - 반응형 웹에서 퍼센트를 대체할 새로운 단위 - viewport 의 initial 컨테이닝 블록의 값, 100 분의 1
    - 보통 full w / h 를 만들때 100vh , 100vw 를 쓴다
    ![containing-box](https://github.com/hogyun3709/Blog-Dev/blob/master/blog-dev-docs/containingBox.png)

    
    
### :horse: MongoDB
***
