<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello-world/>
    <input id="input" v-model="newMsg"/>
    <div id="container">
      <p>{{newMsg}}</p>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

function realDom() {
  console.log('真实dom结构：' + document.getElementById('container').innerHTML);
};
function showData(process,obj){
  console.log(process);
  console.log('data 数据：' + obj.test)
  console.log('挂载的对象：')
  console.log(obj.$el)
  realDom();
  console.log('---------showData---------')
}

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data (){
    return{
      newMsg:"msg",
    }
  },

  /**
   * 由于app.vue是作为组件存在
   * 需要整个组件构建显示完之后 这个vue实例初始化完成之后 才可以realDom 否则取不到 container对象
   */
  beforeCreate:function () {
    console.log("beforeCreate 创建前状态----");
//    showData("beforeCreate",this);
    console.log("$el:" + this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  created:function () {
    console.log("created 创建完毕状态---");
//    showData("created",this);
    console.log("$el:" + this.$el);
    console.log("$data:" + this.$data);
    console.log(this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  beforeMount:function () {
    console.log("beforeMount 挂载前状态---");
//    showData("beforeMount",this);
    console.log("$el:" + (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  mounted:function () {
    console.log("mounted 挂载结束后状态---");
    showData("mounted",this);
    console.log("$el:" + (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  beforeUpdate:function () {
    console.log("beforeupdate:更新之前---");
    showData("beforeUpdate",this);
    console.log("$el:" + (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  updated:function () {
    console.log("updated:数据更新之后---");
    showData("updated",this);
    console.log("$el:"+ (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  beforeDestroy:function () {
    console.log("beforeDestroy:数据销毁之前---");
    showData("beforeDestroy",this);
    console.log("$el:"+(this.$el));
    console.log(this.$el);
    console.log("$data" + this.$data);
    console.log("msg:"+ this.newMsg);
    console.log("--------------------------");
  },
  destroyed:function () {
    console.log("destroyed:数据销毁之后 ---");
    showData("destroyed",this);
    console.log("$el:" + (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
