# Object.defineProperty介绍
## 1.介绍
* 直接在一个对象上定义一个新属性，或者修改一个对象的现有属性，并返回此对象
## 2.语法
* `Object.defineProperty(obj,prop,descriptor)`
  * `descriptor`是对象
* get和set方法不能直接使用，实际上是在赋值和取值时自动调用这两个方法
```js
let obj = {}
Object.defineProperty(obj,'name',{
  // value : '李四',
  // writable : true,
  set(newValue) {
    oValue  = newValue
    console.log('-set-')
  },
  get() { 
    console.log('-get-')
    return oValue
  }
})
obj.name//get
obj.name = 10//set
```