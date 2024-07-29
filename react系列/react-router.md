# 1. 路由导航传参
**searchParams传参：**
```javascript
navigate('/article?id=100&name=jack')
const [params] = userSearchParams()
let id = params.get('id')
```
**params传参：**params传参需注意在路由路径上也做相应改变
```javascript
  navigate('/article/100')
  const params = useParams()
  let id = params.id
```
```javascript
  <!-- 路由配置文件 -->
  {
    path: '/article/:id',
    element: <Article />
  }
```
# 2. 嵌套路由配置

- 使用 children 属性配置路由嵌套关系
  ```javascript
  {
    path: '/',
    element: <Layout />,
    children: [
      {
        path: 'board',
        element: <Board />,
      },
      {
        path: 'about',
        element: <About />
      }
    ]
  }
  ```

- 使用 `<Outlet/>` 组件配置二级路由渲染位置
```javascript
  const Layout = () => {
    return (
      <div>
        <div>我是Layout</div>
        <Link to="/board">面板</Link>
        <Link to="/about">关于</Link>
        {/* 二级路由出口 */}
        <Outlet />
      </div>
    )
  }
```
- 默认二级路由
  当访问的是一级路由时，默认的二级路由组件可以得到渲染，只需要在二级路由的位置去掉path，设置index属性为true.
  ```javascript
    children: [
      {
        index: true,
        element: <Board />,
      },
      {
        path: 'about',
        element: <About />,
      }
    ]
  ```


# 3. 404路由配置
场景：当浏览器输入url的路径在整个路由配置中都找不到对应的 path，为了用户体验，可以使用 404 兜底组件进行渲染.

实现步骤：
1. 准备一个NotFound组件
2. 在路由表数组的末尾，以*号作为路由path配置路由.
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231101100136.png" alt="Pasted image 20231101100136" style="zoom:80%;" />


# 4. 两种路由模式

history模式和hash模式, `ReactRouter`分别由` createBrowerRouter` 和 `createHashRouter `函数负责创建.

![Pasted image 20231101100503](D:\workSoftware\typora\workspace\图片\Pasted image 20231101100503.png)
