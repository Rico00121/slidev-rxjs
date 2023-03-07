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
layout: intro
---

## RxJS是什么？

<br />
<br />

<div class="grid grid-cols-2 gap-x-4">
<div>
<br />
<br />
<br />

- 一个 javascript 的工具库
- Reactive Programming 编程范式的具体实现
- 用于通过使用可观察序列来组合异步和基于事件的程序

</div>

<div>

### Code example

```ts
const observable$$ = new Observable((subscriber) => {
    subscriber.next(1);
    subscriber.next(2);
    //...
    subscriber.complete();
});

//在另一个地方订阅
const subscription 
    = observable$$.subscribe(next => console.log(next));

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
image: 'https://user-images.githubusercontent.com/13499566/138951075-018e65d5-b5fe-4200-9ea7-34315b1764da.jpg'
imageOrder: 1
---

# layout: image-x

imageOrder: 1

image 600x600

<MyBarBottom />

---
layout: image-x
image: 'https://user-images.githubusercontent.com/13499566/138950866-7d2addb2-fe3f-41f5-aab6-d35688516612.jpg'
imageOrder: 2
---

# layout: image-x

imageOrder: 2

image 1080x1920

<BarBottom  title="Slidev theme purplin">
  <Item text="slidevjs/slidev">
    <carbon:logo-github />
  </Item>
  <Item text="Slidevjs">
    <carbon:logo-twitter />
  </Item>
  <Item text="sli.dev">
    <carbon:link />
  </Item>
</BarBottom>

---
layout: quote
position: center
---

# "layout: quote"
position: center

'position' variants: left (default), center, right

<MyBarBottom />

---

# What is Slidev?

Slidev is a slides maker and presenter designed for developers, consist of the following features

- 📝 **Text-based** - focus on the content with Markdown, and then style them later
- 🎨 **Themable** - theme can be shared and used with npm packages
- 🧑‍💻 **Developer Friendly** - code highlighting, live coding with autocompletion
- 🤹 **Interactive** - embedding Vue components to enhance your expressions
- 🎥 **Recording** - built-in recording and camera view
- 📤 **Portable** - export into PDF, PNGs, or even a hostable SPA
- 🛠 **Hackable** - anything possible on a webpage

<br>
<br>

Read more about [Why Slidev?](https://sli.dev/guide/why)

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
layout: image-right
image: 'https://user-images.githubusercontent.com/13499566/138950614-52ec045b-aa93-4d52-91df-b782cc9c7143.jpg'
---

# Code

Use code snippets and get the highlighting directly!

```ts
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = {...user, ...update}  
  saveUser(id, newUser)
}
```

<MyBarBottom />

---
layout: center
class: "text-center"
---

# Learn More

[Documentations](https://sli.dev) / [GitHub Repo](https://github.com/slidevjs/slidev)

<MyBarBottom />
