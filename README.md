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
