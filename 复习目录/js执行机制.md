[Toc]

## 一、线程（浏览器常驻线程）

### 1、js引擎线程
* 解释执行js代码、用户输入、网络请求
### 2、GUI线程
* 绘制用户界面、与js主线程是相斥的
### 3、http网络请求线程
* 处理用户的GET、POST等请求，等返回结果后将回调函数推入任务队列
### 4、定时器触发线程
* 等待时间结束后把执行函数推入任务队列中
### 5、浏览器事件处理线程
* 交互事件发生后将这些事件放入到事件队列中
## 二、js执行机制 - 单线程

```flow
st=>start: js进入执行栈

cond=>condition: 同步？

io1=>inputoutput: 主线程

io2=>inputoutput: Event Table

io3=>inputoutput: 任务全部执行完毕

io4=>inputoutput: Event Quene

e=>end: 读取任务队列中的结果，进入主线程执行

st->cond

cond(yes)->io1->io3->e(right)->io4(right)

cond(no)->io2(right)->io4(right)->e(right)

```

