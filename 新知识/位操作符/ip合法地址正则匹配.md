## 合法ip地址
* 0.0.0.0 ~ 255.255.255.255
## 验证的正则表达式
```js
const reg =
	/(?=(\b|\D))(((\d)|(1\d{1,2})|(2[0-4]\d)|(25[0-5]))\.){3}((\d)|(1\d{1,2})|(2[0-4]\d{1})|(25[0-5]))(?=(\b|\D))/g
let str = '00.00.00.00'
let str2 = '255.255.255.256'
let str3 = '1.1.1'
let str4 = 'a.b.1.4'
let str5 = '1.1.1.1'
console.log(reg.test(str))//false
console.log(reg.test(str2))//false
console.log(reg.test(str3))//false
console.log(reg.test(str4))//false
console.log(reg.test(str5))//true
```
## 注意的地方
* `(?=\b|\D)` 用于界定单词和非数字边界
* `\.` 用于匹配`.`符号