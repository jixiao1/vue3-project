<template>
  <div class="msgCHANGE">
    <div>{{msg}}</div>
    <button @click="changeMSG">改变msg</button>
    <button @click="sendMsg">获取msg</button>
    <div class="red"></div>
    <div :class="myClass"></div>
     <h2>class绑定多个属性</h2>
     <div :class="{'activce':isActive, 'red1': isRed}"></div>
     <div class="blue" :class="{'activce':isActive}"></div>
     <div :class="['error', 'p[osi']">div</div>
     <div :class="[Error, RIGHT]">div</div>
      <h2>绑定多个style</h2>
      <div :style="'color:'+color1">0000000000000</div>
     <div :style="{'color': Color, 'fontSize': FontSize}">绑定多个style</div>
     <div :style="object">3333388888888</div>
     <div :style="[style1, style2]">999999999999999999</div>
     <div>
       <ul>
         <li v-for="(item ,index) in list" :key="index" :class="{'aaa': index == 0, 'bbb': index ==1}">
           {{item}}----{{index}}
         </li>
          <li v-for="(item ,index) in list" :key="index" :style="[index == 0 ? active1 : null, index ==1 ? active11: null]">
           {{item}}----{{index}}
         </li>
       </ul>
     </div>
     <div v-for="(value,key,index) in obj22" :key="key">
       {{value}}---{{key}}---{{index}}
     </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'msg titler',
      myClass: 'red',
      isActive: true,
      isRed: true,
      Error: 'error`1',
      RIGHT: 'RIGHT1  `11',
      Color: 'blue',
      color1: 'orange',
      FontSize: '20px',
      list: ['1111', '222', '33333'],
      obj22: {
        name: '39393',
        age: 29200
      },
      active1: {
        color: 'red'
      },
      active11: {
        color: 'blue'
      },
      object: {
        'color': 'red',
        'fontSize': '50px'
      },
      style1: {
        width: '200px',
        height: '200px'
      },
      style2: {
        backgroundColor: 'red'
      }
    }
  },
  methods: {
    changeMSG () {
      this.msg = 'msg change'
    },
    sendMsg () {
      alert(this.msg)
    }
  }
}
</script>

<style lang="scss">
.msgCHANGE {
  text-align: center;
  width: 100px;
  position: absolute;
  left: 300px;
  top: 0;
  height: 100px;
  background-color: orange;
  margin: 0 auto;
  .red {
    width: 200px;
    height: 300px;
    background-color: palegoldenrod;
    margin: 10px;
  }
  .activce {
    width: 200px;
    height: 200px;
  }
  .aaa {
    color: red;
  }
  .bbb {
    color: blue;
  }
  .red1 {
    background-color: yellowgreen;
  }
}
</style>
