# this指向问题
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