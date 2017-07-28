---
title: redux
date: 2017-03-28 18:06:37
tags:
- RN技术
categories:
- react
---
# redux

## 推荐文档

1. redux 生态系统:http://cn.redux.js.org/docs/introduction/Ecosystem.html
1. 中文官方文档: http://cn.redux.js.org/index.html
2. 英文官方文档: http://redux.js.org/
3. github精简教程: https://github.com/react-guide/redux-tutorial-cn#redux-tutorial

## 什么是redux
1. 随着 JavaScript 单页应用开发日趋复杂，JavaScript 需要管理比任何时候都要多的 state （状态）。
2. 通过限制更新发生的时间和方式，Redux 试图让 state 的变化变得可预测。

3. Redux是JS状态容器.提供可预测化的状态管理. 


## 三大原则

1. 单一数据源
    * 整个应用的 state 被储存在一棵 object tree 中，并且这个 object tree 只存在于唯一一个 store 中。

2. State 是只读的
    * 惟一改变 state 的方法就是触发 action，action 是一个用于描述已发生事件的普通对象。
    
3. 使用纯函数来执行修改
    * 为了描述 action 如何改变 state tree ，你需要编写 reducers。
    
    
## 现实案例
公司项目代码trunk管理

|...|对应关系| 职责|
|:---:|:---:|:---:|
|我们|action |表达修改trunk   代码的意图|
|双星级想出来的修改的方法|reducers |改变公司代码|
|双星级 |combine reducer |reducers集合|
|trunk |store |存储公司代码状态的地方|





## Action 

* 表达我们修改store的意图
* 只是描述了有事情发生了这一事实，并没有指明应用如何更新 state
*   store 数据的唯一来源
*   一般来说你会通过 store.dispatch() 将 action 传到 store    
* Action 创建函数
    * 在 Redux 中的 action 创建函数只是简单的返回一个 action
```javascript
function addTodo(text) {
  return {
    type: ADD_TODO,
    text
  }
}
```
Action.js
```javascript
/*
 * action 类型
 */

export const ADD_TODO = 'ADD_TODO';
export const TOGGLE_TODO = 'TOGGLE_TODO'
export const SET_VISIBILITY_FILTER = 'SET_VISIBILITY_FILTER'

/*
 * 其它的常量
 */

export const VisibilityFilters = {
  SHOW_ALL: 'SHOW_ALL',
  SHOW_COMPLETED: 'SHOW_COMPLETED',
  SHOW_ACTIVE: 'SHOW_ACTIVE'
}

/*
 * action 创建函数
 */

export function addTodo(text) {
  return { type: ADD_TODO, text }
}

export function toggleTodo(index) {
  return { type: TOGGLE_TODO, index }
}

export function setVisibilityFilter(filter) {
  return { type: SET_VISIBILITY_FILTER, filter }
}
```

## Reducer 
* Action 只是描述了有事情发生了这一事实，并没有指明应用如何更新 state。而这正是 reducer 要做的事情。
* Action 处理
    * reducer 就是一个纯函数，接收旧的 state 和 action，返回新的 state。
* 不要直接修改 state。 使用 Object.assign() 新建了一个副本。不能这样使用 Object.assign(state, { visibilityFilter: action.filter })，因为它会改变第一个参数的值。你必须把第一个参数设置为空对象。你也可以开启对ES7提案对象展开运算符的支持, 从而使用 { ...state, ...newState } 达到相同的目的。
  
* 在 default 情况下返回旧的 state。遇到未知的 action 时，一定要返回旧的 state。
* 在写reducer时候,注意store的数据结构

## 纯函数 
* 纯函数是指 不依赖于且不改变它作用域之外的变量状态的函数。
* 也就是说， 纯函数的返回值只由它调用时的参数决定 ，它的执行不依赖于系统的状态（比如：何时、何处调用它）。



![](/img/ReduxFlow.png)

#### connect([mapStateToProps], [mapDispatchToProps], [mergeProps], [options])

#### [mapStateToProps(state, [ownProps]): stateProps]

* (Function): 如果定义该参数，组件将会监听 Redux store 的变化。任何时候，只要 Redux store 发生改变，mapStateToProps 函数就会被调用。
* 该回调函数必须返回一个纯对象，这个对象会与组件的 props 合并。
* 如果你省略了这个参数，你的组件将不会监听 Redux store。
* 如果指定了该回调函数中的第二个参数 ownProps，则该参数的值为传递到组件的 props，而且只要组件接收到新的 props，mapStateToProps 也会被调用（例如，当 props 接收到来自父组件一个小小的改动，那么你所使用的 ownProps 参数，mapStateToProps 都会被重新计算）。

#### [mapDispatchToProps(dispatch, [ownProps]): dispatchProps] 
* (Object or Function): 如果传递的是一个对象，那么每个定义在该对象的函数都将被当作 Redux action creator，而且这个对象会与 Redux store 绑定在一起，其中所定义的方法名将作为属性名，合并到组件的 props 中。
* 如果传递的是一个函数，该函数将接收一个 dispatch 函数，然后由你来决定如何返回一个对象，这个对象通过 dispatch 函数与 action creator 以某种方式绑定在一起（提示：你也许会用到 Redux 的辅助函数 bindActionCreators()）。
* 如果你省略这个 mapDispatchToProps 参数，默认情况下，dispatch 会注入到你的组件 props 中。
* 如果指定了该回调函数中第二个参数 ownProps，该参数的值为传递到组件的 props，而且只要组件接收到新 props，mapDispatchToProps 也会被调用。
     



















