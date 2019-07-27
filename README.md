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

### :green_apple: Node.js
***

### :cyclone: React.js
***

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
