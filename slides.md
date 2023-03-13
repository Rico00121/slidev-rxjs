---
theme: ./theme
title: RxJS
---
# RxJS

用响应式编程来改善你的 Web 应用

<div class="pt-12">
  <span @click="next" class="px-2 p-1 rounded cursor-pointer hover:bg-white hover:bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<MyBarBottom />

---
layout: image-x
image: 'images\RxJS-custom-operators.jpg'
imageOrder: 2
---

## RxJS是什么？
### What is RxJS

<br />

<div style="padding-right: 40px;">

- 一个 javascript 的工具库
- Reactive Programming 编程范式的具体实现
- 基于事件的 “Lodash”

</div>

<MyBarBottom />

---
layout: intro
---

<br />
<br />

<div class="grid grid-cols-2 gap-x-4">
<div style="padding-left: 20px;">
<br />
<br />


## 核心关注点
### Core steps

<br />

- 创建
- 订阅
- 执行
- 清理


</div>

<div>

### Code example

```ts
const observable$ = new Observable((subscriber) => {
    subscriber.next(1);
    subscriber.next(2);
    //...
    subscriber.complete();
});

//在另一个地方订阅
const subscription 
    = observable$.subscribe(
        {
          next: x => console.log('got value ' + x),
          error: err => console.error('error occurred: ' + err),
          complete: () => console.log('done'),
        });

//取消订阅
subscription.unsubscribe();
```
</div>
</div>

<MyBarBottom />

---
layout: intro
---

## 传统函数调用与Observables的区别
### Observable 可以随着时间的推移返回多个值，这是函数所做不到的

<br />
<br />

<div class="grid grid-cols-2 gap-x-4">
<div>

传统的函数调用 -> Pull system
- 生产者（Passive）
  - 在请求的时候返回数据
- 消费者（Active）
  - 需要的时候去请求

### func.call() 意思是 "同步的给我一个值"
</div>
<div>

RxJS -> Push system
- 生产者（Active）
  - 自己主动推送消息给消费者（rxjs中的观察者）
- 消费者（Passive） 
  - 对接收到的数据做出反应 

### observable.subscribe() 意思是 "给我任意数量的值，无论是同步还是异步"
</div>
</div>

<MyBarBottom />

---
layout: image-x
image: 'images\rocket.jpg'
imageOrder: 1
---

## Observable的卫星类型
### Core type

<br/>

<br/>

#### Observer

<br/>

#### Subject

<br/>

#### Scheduler

<br/>

<MyBarBottom />

---
layout: quote
position: center
---

# Operators
The most useful part

以声明方式轻松组合复杂异步代码的基本部分

<MyBarBottom />

---

# 创建型操作符

用于创建具有一些常见预定义行为的Observable

### 一些常见的创建型操作符

|                        |                                                                                                                         |
|------------------------|-------------------------------------------------------------------------------------------------------------------------|
| <kbd>of()</kbd>        | 将参数转换成一个Observable。                                                                       |
| <kbd>interval()</kbd>  | 创建一个按指定的时间间隔发送有序数字的Observable。     |
| <kbd>from()</kbd>      | 从一个可迭代对象，Promise对象或者Observable对象创建。Observable |
| <kbd>fromEvent()</kbd> | 创建一个 Observable，它发出来自给定事件目标的特定类型的事件。                         |
| <kbd>iif()</kbd>       | 在订阅时检查一个布尔值，并在两个可观察源之一之间进行选择。                                |
| <kbd>timer()</kbd>     | 创建一个将等待指定时间段的可观察对象。                                     |           

<MyBarBottom />

---

# 联接创建型操作符

组合多个 Observables 用以创建新的 Observable

### 一些常见的创建型操作符

|                            |                                                                                                                                                       |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| <kbd>forkJoin()</kbd>      | 等待 Observables 完成，然后合并它们发出的最后值；如果传递空数组，则立即完成。                      |
| <kbd>combineLatest()</kbd> | 每当任何输入 Observable 发出一个值时，它都会使用所有输入的最新值组合并发出。 |
| <kbd>contact()</kbd>       | 通过顺序发射它们的值将多个 Observable 连接在一起，当前一个完成后，才会开启下一个。|
| <kbd>merge()</kbd>         | 将多个 Observable 扁平化在一起，当作一条事件流来接收。                                                       |
| <kbd>partition()</kbd>           | 它类似于过滤器，但返回两个 Observable：一个类似于过滤器的输出，另一个具有未通过条件的值。                                                             |

<MyBarBottom />

---

# 管道型操作符

使用语法 observableInstance.pipe(operator()) 通过管道连接到Observables的类型

### 一些常见的管道型操作符

|                                                          |                                                                                                                                                                |
|----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <kbd>map()</kbd>/<kbd>filter()</kbd>/<kbd>reduce()</kbd> | 类似于数组中相应函数的操作。|
| <kbd>scan()</kbd> | 它就像 reduce，但在每次更新后发出当前累积状态。|
| <kbd>take()</kbd>                                        | 长从源中获取指定数量前n个值，然后完成。                                                                                                  |
| <kbd>throttle()</kbd>                                    | 从源 Observable 发出一个值，然后在另一个 Observable 确定的持续时间内忽略后续源值，然后重复此过程。    |
| <kbd>debounce()</kbd>                                    | 只有在另一个 Observable 确定的特定时间跨度过去而没有另一个源发射时，才从源 Observable 发出通知。 |
| <kbd>tap()</kbd>                                         | 用于对来自源可观察对象的通知执行副作用。                                                                                     |

<MyBarBottom />


---
layout: center
class: "text-center"
---

# Learn More

[Documentations](https://rxjs.dev/guide/operators) / [GitHub Repo](https://github.com/ReactiveX/rxjs)

<MyBarBottom />
