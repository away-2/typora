### 一、类型声明

使用 **:** 来对变量或函数形参，进行类型声明

```javascript
let a: string  // 变量a只能存储字符串
let b: number  // 变量b只能存储数值
let c: boolean  // 变量c只能存储布尔值

a = 'hello'
a = 100   //警告：不能将类型“number”分配给类型“string”

b = 666
b = 'hi'  // 警告：不能将类型“string”分配给类型“number”

c = true
c = 110   // 警告：不能将类型“number”分配给类型“boolean”

// 参数x必须是数字，参数y也必须是数字，函数返回值也必须是数字
function add(x: number, y: number):number {
    return x + y
}

add(1, 2)
add(a, 2)  // 警告：类型“string”的参数不能赋给类型“number”的参数
```

在 **:** 后也可以写字面量类型，不过实际开发中用的不多

### 二、类型推断

**TS** 会根据我们的代码，进行类型推导，例如下面代码中的变量d，只能存储数字

```javascript
let d = -99  // TypeScript会推断出变量d的类型是数字
d = false    // 警告：不能将类型“boolean”分配给类型“number”
```

但要注意，类型推断不是万能的，面对复杂类型时推断容易出问题，所以尽量还是明确的编写类型声明！

### 三、类型总览

#### **JavaScript中的数据类型**

- string
- number
- boolean
- null
- undefined
- bigint
- symbol
- object（object包括Array、Function、Date、Error等......）

#### **TypeScript中的数据类型**

- 上诉所有JavaScript类型
- 六个 新类型
  - any
  - unknow
  - never
  - void
  - tuple
  - enum
- 两个用于自定义类型的方法
  - type
  - interface

#### **注意点！！**

在`Javascript`中的这些内置构造函数：`Number`、`String`、`Boolean`，它们用于创建对应的包装对象，在日常开发时很少使用，在`TypeScript`中进行类型声明时，通常都是用小写的`number`、`string`、`boolean`

例如下面代码：

```javascript
let str1: string
str1 = 'hello'
str1 = new String('hello')  // 报错

let str2: String
str2 = 'hello'
str2 = new String('hello')

console.log(typeof str1)  // string
console.log(typeof str1)  // object
```

- **原始类型 VS 包装对象**
  - **原始类型**： 如`number`、`string`、`boolean`，在`JavaScript` 中是简单数据类型，它们在内存中占用空间少，处理速度快。
  - **包装对象**： 如`Number`对象、`String`对象、`Boolean`对象，是复杂类型，在内存中占用更多空间，在日常开发时很少由开发人员自己创建包装对象
- **自动装箱：** `Javascript` 在必要时会自动将原始类型包装成对象，以便调用方法或访问属性

### 四、常用类型

#### 1. `any`

`any`的含义是：任意类型，一旦将变量类型限制为`any`，那就意味着放弃了对该变量的类型检查。

```javascript
// 明确的表示a的类型是 any —— 【显式的any】
let a: any
// 以下对a的赋值，均无警告
a = 100
a = 'hello'
a = false

// 没有明确的表示b的类型是any，但TS主动推断出来b是any —— 隐式的any
let b
// 以下对b的赋值，均无警告
b = 100
b = 'hello'
b = false

```

注意点：`any`类型的变量，可以赋值给任意类型的变量

#### 2. `unknown`

- `unknown`可以理解为一个类型安全的`any`，适用于：不确定数据的具体类型

  ```javascript
  // 设置a的类型是 unknown
  let a: unknown
  // 以下对a的赋值，均正常
  a = 100
  a = 'hello'
  a = false
  
  // 设置x的数据类型为string
  let x: string
  x = a   // 警告：不能将类型“unknown”分配给类型“string”
  ```

  

- `unknown`会强制开发者在使用之前进行类型检查，从而提供更强的类型安全性。

  ```javascript
  // 设置x的数据类型为string
  let x: string
  
  // 设置a的类型是 unknown
  let a: unknown
  a = 'hello'
  
  // 第一种方式：加类型判断
  if(typeof a === 'string') {
      x = a
      console.log(x)
  }
  
  // 第二种方式：加断言
  x = a as string
  
  // 第三种方式：加断言
  x = <string>a
  ```

  

- 读取`any`类型数据的任何属性都不会报错，而`unknown`正好相反

  ```javascript
  let str1: string
  str1 = 'hello'
  str1.toUpperCase()  // 无警告
  
  let str2: any
  str2 = 'hello'
  str2.toUpperCase()  // 无警告
  
  let str3: unknown
  str3 = 'hello'
  str3.toUpperCase()  // 警告：“str3”的类型为“未知”
  
  // 使用断言强制指定str3的类型为string
  (str3 as string).toUpperCase()  // 无警告
  ```

  

#### 3. `never`

`never`的含义是：任何值都不是，简而言之就是不能有值，`undefined`、`null`、`''`、`0` 都不行！

- 几乎不用`never`去直接限制变量，因为没有意义，例如：

  ```javascript
  // 指定a的类型为never，那就意味着a以后不能存任何的数据了
  let a: never
  
  // 以下对a的所有赋值都会有警告
  a = 1
  a = true
  a = undefined
  a = null
  a = boolean
  a = 'hello'
  ```

- `never`一般是`TypeScript`主动推断出来的， 例如

  ```javascript
  // 指定a的类型为string
  let a: string
  // 给a设置一个值
  a = 'hello'
  
  if(typeof a === 'string'){
      console.log(a.toUpperCase())
  } else {
      console.log(a) // TypeScript会推断出此处的a是never，因为没有任何一个值符合此处的逻辑
  }
  ```

- `never`也可用于限制函数的返回值

  ```javascript
  // 限制throwError函数不需要有任何返回值，任何值都不行，像undefined、null都不行
  function throwError(str: string): never {
      throw new Error("程序异常退出:" + str)
  }
  ```

  

#### 4. `void`

- `void`通常用于函数返回值声明，含义：【函数不返回任何值，或者说返回值为空，调用者也不应该依赖其返回值进行任何操作】

  ```javascript
  function logMessage(msg: string): void{
      console.log(msg)
  }
  logMessage('hello')
  ```

  

  注意：编码者没有编写`return`去指定函数的返回值，所以`logMessage`函数是没有**显式返回值**的，但会有一个**隐式返回值**，就是`undefined`；即：虽然函数返回类型为`void`,但也是可以接受`undefined`的，简单记：**`undefined`是`void`可以接受的一种“空”。**

- 以下写法均符合规范

  ```javascript
  // 无警告
  function logMessage1(msg: string): void{
      console.log(msg)
  }
  
  // 无警告
  function logMessage2(msg: string): void{
      console.log(msg)
      return
  }
  
  // 无警告
  function logMessage3(msg: string): void{
      console.log(msg)
      return undefined
  }
  ```

- 那限制函数返回值时，是不是`undefined`和`void`就没区别呢？ 有区别，因为还有这句话：**【返回值类型为`void`的函数，调用者不应该依赖其返回值进行任何操作！】**对比下面两段代码：

  ```javascript
  function logMessage(msg: string): void{
      console.log(msg)
  }
  
  let res = logMessage('hello')
  if(res) { // 此行报警告
      console.log('logMessage有返回值')
  }
  
  ```

  ```javascript
  function logMessage(msg: string): undefined{
      console.log(msg)
  }
  
  let res = logMessage('hello')
  if(res) { // 此行无警告
      console.log('logMessage有返回值')
  }
  ```

  **理解void和undefined**

  ​	I. `void`是一个广泛的概念，用来表达“空”，而`undefined`则是这种“空”的具体表现之一。

  ​	II. 因此可以说`undefined`是`void`能接受的“空”状态的一种具体形式。

  ​	III. 换句话说：`void` 包含`undefined`，但`void`表达的语义超越了单纯的`undefined`，它是一种意图上的约定，而不仅仅是特定值的限制。

  **总结：**若函数返回类型为`void`，那么:

    I. 从语法上讲：函数是可以返回`undefined`的，至于显示返回，还是隐式返回，这无所谓！

    II. 从语义上讲：函数调用者不应关心函数返回的值，也不应该依赖返回值进行任何操作！即使返回了`undefined`值。

#### 5. `object`

关于`object`和`Object`，直接说结论：实际开发中用的相对较少，因为范围太大了。

##### `object`(小写)

`object`的含义是：所有**非原始类型**，可存储：对象、函数、数组等，由于限制的范围**比较宽泛**，在实际开发中使用的**相对较少**。

```javascript
let a: object    // a的值可以是任何【非原始类型】，包括：对象、函数、数组等

// 以下代码，是将【非原始类型】赋给a，所以均符合要求
a = {}
a = {name: 'hello'}
a = [1, 3, 5]
a = function(){}
a = new String('123')
class Person {}
a = new Person()

// 以下代码，是将【原始类型】赋给a，有警告
a = 1    // 警告：不能将类型“number”分配给类型“object”
a = true    // 警告：不能将类型“boolean”分配给类型“object”
a = 'hello'    // 警告：不能将类型“string”分配给类型“object”
a = null   // 警告：不能将类型“null”分配给类型“object”
a = undefined    // 警告：不能将类型“undefined”分配给类型“object”
```



##### `Object`（大写）

1. 官方描述：所有可以调用`Object`方法的类型。

2. 简单记忆：除了`undefined`和`null`的任何值。

3. 由于限制的范围实在太大了！所以实际开发中使用频率极低。

```javascript
let b: Object  // b的值必须是Object的实例对象（除去undefined和null的任何值）
// 以下代码，是将【非原始类型】赋给a，所以均符合要求
b = {}
b = {name: 'hello'}
b = [1, 3, 5]
b = function(){}
b = new String('123')
class Person {}
b = new Person()
b = 1    
b = true    
b = 'hello'  

 // 以下代码，是将【原始类型】赋给b，有警告 
b = null   // 警告：不能将类型“null”分配给类型“object”
b = undefined    // 警告：不能将类型“undefined”分配给类型“object”
```

##### 声明对象类型

1. 实际开发中，限制一般对象，通常使用以下形式

   ```javascript
   // 限制person1对象必须有name属性，age为可选属性
   let person1: { name: string, age?: number}
   
   // 含义同上，也能用分号做分隔
   let person2: { name: string; age?: number}
   
   // 含义同上，也能用换行做分隔
   let person3: {
       name: string
       age?: number
   }
   
   // 如下赋值均可
   person1 = {name: 'hello', age: 18}
   person2 = {name: 'hello'}
   person3 = {name: 'hello'}
   
   // 如下赋值不合法，因为person3的类型限制中，没有对gender属性的说明
   person3 = {name: 'hello', gender: 'man'}  // 警告：对象字面量只能指定已知属性，并且“gender”不在类型“{ name: string; age?: number | undefined; }”中
   ```

​          2. 索引签名： 允许定义对象可以具有任意数量的属性，这些属性的键和类型是可变的，常用于：描述类型不确定的属性，（具有动 态属性的对象）。

```javascript
// 限制person对象必须有name属性，可选age属性但值必须是数字，同时可以有任意数量、任意类型的属性
let person: {
  name: string;
  age?: number;
  [key: string]: any; // 索引签名，完全可以不用key这个单词，换成其他都行
};

// 赋值合法
person = {
  name: "hello",
  age: 18,
  gender: "man",
};
```

##### 声明函数类型

```javascript
let count: (a: number, b: number) => number

count = function (x, y) {
    return x + y
}
```

备注： 

`TypeScript`中的`=>` 在函数式声明时表示函数类型，描述其参数类型和返回类型。

`JavaScript` 中的`=>` 是一种定义函数的语法，是具体的函数实现。

函数类型声明还可以使用：接口、自定义类型等方式，详见下文。

##### 声明数组类型

```javascript
let arr1: string[]
let arr2: Array<string>

arr1 = ['a', 'b', 'c']
arr2 = ['a', 'b']
```

备注： 上诉代码中的`Array<string>` 属于泛型，详见下文。

#### 6. `tuple`

元组`(Tuple)`是一种特殊的**数组类型**，可以存储固定数量的元素，并且每个元素的类型是已知的且可以不同。元组用于精确描述一组值的类型，`?` 表示可选元素。

```javascript
// 第一个元素必须是 string 类型，第二个元素必须是 number 类型
let arr1: [string,number]
// 第一个元素必须是 number 类型，第二个元素是可选的，如果存在，必须是 boolean 类型
let arr2: [number,boolean?]
// 第一个元素必须是 number 类型，后面的元素可以是任意数量的 string 类型
let arr3: [number,...string[]]

// 可赋值
arr1 = ['hello', 123]
arr2 = [100, false]
arr2 = [200]
arr3 = [100, 'hello', 'world']
arr3 = [100]

// 不可赋值
arr1 = ['123', 123, false]  // 报警：不能将类型“[string, number, boolean]”分配给类型“[string, number]”
```

#### 7.  `enum`

枚举(`enum`)可以定义**一组命名常量**，它能增强代码**可读性**，也让代码**更好维护**。

如下代码的功能是：根据`walk`时传入的不同参数，执行不同的逻辑，存在的问题是调用`walk`时传参没有任何提示，编码者很容易写错字符串内容；并且用于判断逻辑的`up`,`down`, `left`, `right`是**连续且相关 一组值**，那此时就特别适合使用**枚举**（`enum`）。

```javascript
function walk(str: string) {
  if (str === "up") {
    console.log("上");
  } else if (str === "down") {
    console.log("下");
  } else if (str === "left") {
    console.log("左");
  } else if (str === "right") {
    console.log("右");
  } else {
    console.log('error');   
  }
}

walk('up')
walk('down')
walk('left')
walk('right')
```

##### 数字枚举





