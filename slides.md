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
    = observable$.subscribe(next => {
        //响应收到的值，做一些操作
        console.log(next);
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
| <kbd>of()</kbd>        | Converts the arguments to an observable sequence.                                                                       |
| <kbd>interval()</kbd>  | Creates an Observable that emits sequential numbers every specified interval of time, on a specified SchedulerLike.     |
| <kbd>from()</kbd>      | Creates an Observable from an Array, an array-like object, a Promise, an iterable object, or an Observable-like object. |
| <kbd>fromEvent()</kbd> | Creates an Observable that emits events of a specific type coming from the given event target.                          |
| <kbd>iif()</kbd>       | Checks a boolean at subscription time, and chooses between one of two observable source.                                |
| <kbd>timer()</kbd>     | Creates an observable that will wait for a specified time period.                                                       |           

<MyBarBottom />

---

# 联接创建型操作符

组合多个 Observables 用以创建新的 Observable

### 一些常见的创建型操作符

|                            |                                                                                                                                                       |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| <kbd>forkJoin()</kbd>      | Wait for Observables to complete and then combine last values they emitted; complete immediately if an empty array is passed.                         |
| <kbd>combineLatest()</kbd> | Whenever any input Observable emits a value, it computes a formula using the latest values from all the inputs, then emits the output of that formula. |
| <kbd>contact()</kbd>       | Concatenates multiple Observables together by sequentially emitting their values, one Observable after the other.|
| <kbd>merge()</kbd>         | Flattens multiple Observables together by blending their values into one Observable.                                                       |
| <kbd>partition()</kbd>           | It's like filter, but returns two Observables: one like the output of filter, and the other with values that did not pass the condition.                                                              |

<MyBarBottom />

---

# 管道型操作符

使用语法 observableInstance.pipe(operator()) 通过管道连接到Observables的类型

### 一些常见的管道型操作符

|                                                          |                                                                                                                                                                |
|----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <kbd>map()</kbd>/<kbd>filter()</kbd>/<kbd>reduce()</kbd> | 类似于数组的操作                                                                                                                                                       |
| <kbd>take()</kbd>                                        | Takes the first count values from the source, then completes.                                                                                                  |
| <kbd>throttle()</kbd>                                    | Emits a value from the source Observable, then ignores subsequent source values for a duration determined by another Observable, then repeats this process.    |
| <kbd>debounce()</kbd>                                    | Emits a notification from the source Observable only after a particular time span determined by another Observable has passed without another source emission. |
| <kbd>tap()</kbd>                                         | Used to perform side-effects for notifications from the source observable.                                                                                     |

<MyBarBottom />


---
layout: center
class: "text-center"
---

# Learn More

[Documentations](https://rxjs.dev/guide/operators) / [GitHub Repo](https://github.com/ReactiveX/rxjs)

<MyBarBottom />
