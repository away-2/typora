## 1. useEffect

    useEffect是一个React Hook函数，用于在React组件中创建不是由事件引起而是由渲染本身引起的操作（副作用）, 比如发送AJAX请求，更改DOM等等.
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030133813.png" alt="Pasted image 20231030133813" style="zoom:80%;" />
    

    说明：上面的组件中没有发生任何的用户事件，`组件渲染完毕之后`就需要和服务器要数据，整个过程属于`“只由渲染引起的操作”`
```javascript
    useEffect 的基础语法：
    useEffect(() => { }, [])
```
    参数1是一个函数，可以把它叫做副作用函数，在函数内部可以放置要执行的操作.
    
    参数2是一个数组（可选参），在数组里放置依赖项，不同依赖项会影响第一个参数函数的执行，当是一个空数组的时候，副作用函数只会在组件渲染完毕之后执行一次.
    
    依赖项参数说明

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030134438.png" alt="Pasted image 20231030134438" style="zoom: 67%;" />
    useEffect清除副作用
    

    在useEffect中编写的`由渲染本身引起的对接组件外部的操作`，社区也经常把它叫做`副作用操作`，比如在useEffect中开启了一个定时器，我们想在组件卸载时把这个定时器再清理掉，这个过程就是清理副作用.

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030134718.png" alt="Pasted image 20231030134718" style="zoom:67%;" />

## 2.  useRef

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030133548.png" alt="Pasted image 20231030133548" style="zoom: 67%;" />

## 3.  useState

    useState 是一个 React Hook（函数），它允许我们向组件添加一个状态变量, 从而控制影响组件的渲染结果.
    
    本质：和普通JS变量不同的是，状态变量一旦发生变化组件的视图UI也会跟着变化（数据驱动视图）

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030133247.png" alt="Pasted image 20231030133247" style="zoom:67%;" /><img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030133339.png" alt="Pasted image 20231030133339" style="zoom: 67%;" />
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030133414.png" alt="Pasted image 20231030133414" style="zoom:67%;" />

## 4.  useImperativeHandle

    `useImperativeHandle` 允许你自定义通过 `ref` 暴露给父组件的实例值。通常，我们使用 `ref` 来访问组件的 DOM 元素或类组件的实例。
    
    基本用法
    
    当你想从子组件向父组件暴露某些特定的方法时，可以使用 `useImperativeHandle`

## 5. useReducer

    作用：和useState的作用类似，用来管理相对复杂的状态数据
    
    useReducer-基础用法
    
    1. 定义一个reducer函数（根据不同的action返回不同的新状态）
    
    2. 在组件中调用useReducer，并传入reducer函数和状态的初始值
    
    3. 事件发生时，通过dispatch函数分派一个action对象（通知reducer要返回哪个新状态并渲染UI）
    
    代码demo
```javascript
import { useReducer } from "react"

// 1. 定义reducer函数 根据不同的action 返回不同的状态

function reducer (state, action) {
  switch (action.type) {
    case 'INC':
      return state + 1
    case 'DEC':
      return state - 1
    case 'SET':
      return action.payload  // 分派action时传参
    default:
      return state
  }
}

// 2. 组件中调用useReducer(reducer, 0) => [state, dispatch]

// 3. 调用dispatch({type:'INC'})=> 通知reducer产生一个新的状态 使用这个新状态更新UI

function App () {
  const [state, dispatch] = useReducer(reducer, 0)
  return (
    <div className="App">
      this is app
      <button onClick={() => dispatch({ type: 'DEC' })}>-</button>
      {state}
      <button onClick={() => dispatch({ type: 'INC' })}>+</button>
      <button onClick={() => dispatch({ type: 'SET', payload: 100 })}>update</button>
    </div>
  )
}

export default App
```

## 6. useCallback

    作用：在组件多次重新渲染的时候缓存函数
    
    useCallback - 基础语法
    
    `useCallback(fn(), [])   // fn()代表被缓存的函数` 
    
    **说明：使用useCallback包裹函数之后，函数可以保证在App重新渲染的时候保持引用稳定**
    
    例子：

![Pasted image 20231103133456](D:\workSoftware\typora\workspace\图片\Pasted image 20231103133456.png)

## 7. useMemo

    https://skillgroup.cn/framework/react/hooks/use-memo.html
    useMemo用于优化性能，特别是在组件重新渲染时。当组件的某些状态或属性发生变化时，useMemo 可以帮助我们避免不必要的计算或渲染。
    
    useMemo - 基础语法
```javascript
useMemo(() => {
  // 根据count返回计算的结果
},[count])
```
    **注意 ：使用useMemo做缓存之后可以保证只有count1依赖项发生变化时才会重新计算**
    
    **用法**
    
    1、跳过代价昂贵的重新计算
    
    useMemo 返回一个 memoized 值。这意味着它会记住上一次的计算结果，并在依赖项没有发生变化时返回该结果，而不是重新计算。这可以帮助避免在每次渲染时进行昂贵的计算。
    
    2、跳过组件的重新渲染
    
    `useMemo`的另一个用途是跳过组件的重新渲染。在某些情况下，我们希望组件的某些属性发生变化时，组件不会重新渲染。这时，我们可以使用`useMemo`来返回组件的 memoized 值，从而避免组件的重新渲染。

## 8. React.memo

    作用：允许组件在Props没有改变的情况下跳过渲染
    
    React组件默认的渲染机制：只要父组件重新渲染子组件就会重新渲染
 ```javascript
    React.memo - 基础语法
    const MemoComponent = memo(function SomeComponent(props) {
      // ...
    })
 ```

    **说明：经过memo函数包裹生成的缓存组件只有在props发生变化的时候才会重新渲染**
    
    React.memo - props的比较机制
    机制: 在使用memo缓存组件之后，React会对每一个 prop 使用 Object.is 比较新值和老值，返回true，表示没有变化
    
    prop是简单类型
    
    Object.is(3, 3) => true 没有变化
    
    prop是引用类型（对象 / 数组）
    
    Object([], []) => false 有变化，React只关心引用是否变化
    
    **总结：传递一个简单类型的props，props变化时组件重新渲染；传递一个引用类型的props，比较的是新值和旧值的引用是否相等，当父组件的函数重新执行时，实际上形成的是新的引用，与上一次是不一样的，当然，如果要保证引用稳定，可以使用useMemo在组件渲染的过程中缓存一个值**

## 9. React.forwarRef

    使用ref暴露DOM节点给父组件

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231103134822.png" alt="Pasted image 20231103134822" style="zoom:50%;" />
    

```javascript

// 子组件
const Son = forwardRef((props, ref) => {
  return <input type="text" ref={ref} />
})
// 父组件
function App () {
  const sonRef = useRef(null)
  const showRef = () => {
    console.log(sonRef)
    sonRef.current.focus()
  }
  return (
    <>
      <Son ref={sonRef} />
      <button onClick={showRef}>focus</button>
    </>
  )
}
```

## 10. 父子通信
- 父传子-基础实现

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231103143437.png" alt="Pasted image 20231103143437" style="zoom: 67%;" />
**实现步骤**

1. 父组件传递数据 - 在子组件标签上绑定属性
2. 子组件接收数据 - 子组件通过props参数接收数据

- 父传子-props说明

1. props可传递任意的数据，数字、字符串、布尔值、数组、对象、函数、JSX
![Pasted image 20231103143707](D:\workSoftware\typora\workspace\图片\Pasted image 20231103143707.png)
2. props是只读对象
   子组件只能读取props中的数据，不能直接进行修改, 父组件的数据只能由父组件修改

##### 父传子 - 特殊的prop children

场景：当我们把内容嵌套在子组件标签中时，父组件会自动在名为children的prop属性中接收该内容

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231103143931.png" alt="Pasted image 20231103143931" style="zoom:67%;" />

#### 父子组件通信-子传父

核心思路：在子组件中调用父组件中的函数并传递参数

![Pasted image 20231103144947](D:\workSoftware\typora\workspace\图片\Pasted image 20231103144947.png)
![Pasted image 20231103145003](D:\workSoftware\typora\workspace\图片\Pasted image 20231103145003.png)

## 11. 兄弟通信

使用状态提升实现兄弟组件通信
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231103145039.png" alt="Pasted image 20231103145039" style="zoom:80%;" />
**实现思路：借助“状态提升”机制，通过父组件进行兄弟组件之间的数据传递

1. A组件先通过子传父的方式把数据传给父组件App

2. App拿到数据后通过父传子的方式再传递给B组件

## 12. 跨层通信

使用Context机制跨层级组件通信
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231103145129.png" alt="Pasted image 20231103145129" style="zoom: 80%;" />
实现步骤：

1. 使用createContext方法创建一个上下文对象Ctx
2. 在顶层组件（App）中通过 Ctx.Provider 组件提供数据
3. 在底层组件（B）中通过 useContext 钩子函数获取数据

## Redux基础

![Pasted image 20231030093431](D:\workSoftware\typora\workspace\图片\Pasted image 20231030093431.png)
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231030095703.png" alt="Pasted image 20231030095703" style="zoom:80%;" />

## 一些遇到的问题

#### 组件卸载时取消异步请求

可以使用 `AbortController` 来取消，这种方法本质上就是在组件卸载时取消副作用

```javascript
const Component = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    const controller = new AbortController();
    fetch(url, { signal: controller.signal }).then((data) => setData(data));
    return () => {
      controller.abort();
    }
  }, []);

  // ...
};

```

