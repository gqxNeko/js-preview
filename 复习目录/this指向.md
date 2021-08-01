## this指向问题
* 全局`this`指向`window`
```js
var a = 10
console.log(this)//window
``` 
* 非箭头函数里的`this`指向`window`
```js
function test(){
  console.log(this)
}
test()
```
* 箭头函数`this`指向
```js
(()=>{
  console.log(this)
})()
```
* 谁调用指向谁
```javascript
Person.prototype = {
  name:'xx',
  sayName:function(){
    console.log(this)
    console.log(this.name)
  }
}
function Person(){
  this.name = 'xxx'
  this.age = 'xx'
}
var person = new Person()
console.log(person)//{name:'xxx',age:'xx'}
// person调用sayName方法，this指向person
person.sayName()//{name:'xxx',age:'xx'} 'xxx'
```