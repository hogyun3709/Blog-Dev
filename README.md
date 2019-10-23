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
  - Use lifesycle function
  ![react-ui-lifeCycle](https://github.com/hogyun3709/Blog-Dev/blob/master/blog-dev-docs/react-ui-lifeCycle.jpg)
  - Will hooks replace classes or redux>
    - Hook 이 앞으로 걸어가야 할 리액트의 방향이긴 하나, Dan Abramov 는 기존의 앱을 훅으로 다시 사용 작성하라고는 권하지 않았다.
    - State Management 부분에서는 도움을 주는 것이 확실하니, 앞으로의 행보를 기대해봐야겠다.
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

### :slot_machine: ML
***
1. Is Faster R-CNN best for object detection?<br>
- Overall topic: All about image classficatiion<br>
  - Reading articles about obj detection<br>
  -[Zero to Hero: Guide to Object Detection using Deep Learning: Faster R-CNN, YOLO, SSD](https://cv-tricks.com/object-detection/faster-r-cnn-yolo-ssd/)
  -[R-CNN, Fast R-CNN, Faster R-CNN, YOLO - Objecet Detectiion Alogirthms](https://towardsdatascience.com/r-cnn-fast-r-cnn-faster-r-cnn-yolo-object-detection-algorithms-36d53571365e)

2. 

### :horse: MongoDB
***
