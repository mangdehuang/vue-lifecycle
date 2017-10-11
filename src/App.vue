<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello-world/>
    <input id="input" v-model="newMsg"/>
    <p>{{newMsg}}</p>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

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
  beforeCreate:function () {
    console.log("beforeCreate 创建前状态----");
    console.log("$el:" + this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  created:function () {
    console.log("created 创建完毕状态---");
    console.log("$el:" + this.$el);
    console.log("$data:" + this.$data);
    console.log(this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  beforeMount:function () {
    console.log("beforeMount 挂载前状态---");
    console.log("$el:" + (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  mounted:function () {
    console.log("mounted 挂载结束后状态---");
    console.log("$el:" + (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  beforeUpdate:function () {
    console.log("beforeupdate:更新之前---");
    console.log("$el:" + (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  updated:function () {
    console.log("updated:数据更新之后---");
    console.log("$el:"+ (this.$el));
    console.log(this.$el);
    console.log("$data:" + this.$data);
    console.log("msg:" + this.newMsg);
    console.log("--------------------------");
  },
  beforeDestroy:function () {
    console.log("beforeDestroy:数据销毁之前---");
    console.log("$el:"+(this.$el));
    console.log(this.$el);
    console.log("$data" + this.$data);
    console.log("msg:"+ this.newMsg);
    console.log("--------------------------");
  },
  destroyed:function () {
    console.log("destroyed:数据销毁之后 ---");
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
