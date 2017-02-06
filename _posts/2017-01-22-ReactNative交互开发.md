---
layout: post
title: React Native交互开发
category: Android
tags: 
- IOS
- ReactNative
---

<p class="message">
  我是做Android出身的，后来由于工作需要，后端、前端都搞过，现在也有了IOS开发经验。从最初对整个互联网架构没有清晰的认识到逐渐熟悉，确实成长了不少。但我一直坚信一个观点，门门精，门门松。所以我给自己定的方向是深入移动客户端开发。语言只是工具，我希望能达到举一反三、触类旁通的效果。前一段时间由于项目的关系接触React Native，立刻被它优雅的设计所吸引。本篇主要讲解React Native的JS和原生的交互，以摇一摇为例。
</p>

大家都清楚，React-Native就是在开发效率和用户体验间做的一种权衡。React-native是使用JS开发，开发效率高、发布能力强，不仅拥有hybrid的开发效率，同时拥有native app相媲美的用户体验。

学习时的[参考网址](https://github.com/vczero/react-native-lesson)
React Native的环境搭建按照[官网](http://reactnative.cn/post/10)操作即可，在此不做介绍。

要理解React Native应用的基本结构，首先需要了解一些基本的React概念，如JSX语法、组件、state状态和props属性。

Node.js基础
JSX语法基础
Flexbox布局

JSX不是必需，而是建议使用的。JSX能更像HTML表达树形结构，JSX只是对JavaScript进行了拓展。

比如：

```
render: function() {
	return (
		<View style={styles.container}>
			<Text style={styles.welcome}>
				Welcome to React Native!
				<!-- 表达式需要{}包裹 -->
				{0? '第一段' : '第二段'}
			</Text>
		</View>
	);
}
```

在HTML中，属性可以是任意值，如：<div tagid="00_1"></div>,tagid就是属性；同样在组件上可以使用属性。

建议使用以下方式：

```
var props = {
	tagid: 'GGEESD',
	poiname: '东方明珠'
};
return (<View {...props}></View>);
```

如果需要在调用组件的时候动态增加或者覆盖属性，又该如何呢？

```
<View {...props} poiname={'虹桥机场'}></View>
```

关于样式  
（1）普通内联样式:{{}},第一层｛｝是表达式，第二层｛｝是js对象；
<View style={{fontSize:40, width:80,}}> </View>
（2）调用样式表:{样式类.属性}
<View style={styles.container}></View>
（3）样式表和内联样式共存:{[]}
<View style={[styles.container, {fontSize:40, width:80}]}>
（4）多个样式表:{[样式类1， 样式类2]}
<View style={[styles.container, styles.color]}>

属性校验
为了实现强类型语言的效果，我们可以使用propTypes来声明数据属性的合法性校验。例如：
React.createClass({
    porpTypes:{
        username: React.PropTypes.string,
        age: React.propTypes.number,
    }
});

设定默认属性
React.createClass({
    getDefaultProps: function(){
        return {
            sign: '这个家伙很懒，什么都没留下'
        };
    }
});

组件的生命周期
componentWillMount：组件创建之前
getInitialState：初始化状态
render：渲染视图
componentDidMount：渲染视图完成后
componentWillUnmount：组件被卸载之前











热更新服务



                                