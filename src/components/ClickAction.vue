<template>
 <div class="clickAction">
    <div>
    <div> {{msg}}</div>
    <button @click="msgChangeAction">修改msg</button>
    <button @click="setmsgChangeAction">获取msg</button>
    <!-- 事件修饰符 -->
    <a href="http://www.baidu.com" target="_blank" @click="stopClcik($event)">百度一下</a>
    <a href="http://www.baidu.com" target="_blank" @click.prevent="stopClick1">百度一下</a>
  </div>
  <div>
    <input type="text" name="" id="" @keyup="serachAction($event)">
  </div>
  <div>
    <input type="text" name="" id="" @keyup.enter="searchAS">
  </div>
 </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Hello World'
    }
  },
  methods: {
    msgChangeAction () {
      this.msg = 'msg Hello World'
    },
    setmsgChangeAction () {
      console.log(this.msg)
    },
    stopClcik (event) {
      console.log(event)
      event.preventDefault();
      
    },
    stopClick1 () {},
    serachAction ($event) {
    //  console.log($event)
     if ($event.keyCode === 13) {
       alert('按下了回车键')
     }
    },
    searchAS () {
     alert('按下了回车键')
    }
  }
}
</script>

<style lang="scss">
.clickAction {
  width: 200px;
  height: 200px;
  background-color: red;
  position: absolute;
  left: 600px;
  top: 10px;
}
</style>