# vue-lifecycle
### 关于vue生命周期的demo
```
 由于app.vue是作为组件存在
 需要整个组件构建显示完之后 这个vue实例初始化完成之后 才可以realDom 否则取不到 container对象
 但是在mounted之后 就可以取到dom  因为已经渲染到界面上了

 所有用引入vue.js的方法可以取得 realdom ,因为他是先有dom
```

