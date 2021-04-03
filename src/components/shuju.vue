<template>
   <div>
     <!--  绑定数据 -->
    <h1> 绑定数据</h1>
    <div class="msg">{{msg}}</div>
    <div v-text="msg" class="msg"></div>
     <h1> 绑定数据html</h1>
    <div v-html="hmsg"></div>
    <!-- 绑定属性 -->
    <h1> 绑定属性</h1>
     <div class="msg">
       <img v-bind:src="src" alt="lof">
     </div>
       <div class="msg">
       <img :src="src" alt="lof">
     </div>
     <div title="123">123456</div>
     <div :title="divtitle">123456</div>
     <!-- 循环数据 -->
      <h1> 循环数据</h1>
      <!-- 普通数组 -->
      <div>
        <ul>
          <li v-for="(item, index) in list" :key="index">
            {{item}}
          </li>
        </ul>
      </div>
       <!-- 数组对象 -->
       <div class="box">
         <ul>
           <li v-for="(item ,index) in list1" :key="index">
             {{item.tite}}
           </li>
         </ul>
       </div>
       <!-- 数组对象嵌套 -->
       <div class="box2">
         <div v-for="(item, index) in list2" :key="index">
           <span>
             {{item.count}}^
             <div v-for="(item1, index1) in item.list" :key="index1">
               <span style="color: red;">{{item1.city}}</span>
             </div>
           </span>
         </div>
       </div>
   </div>
</template>

<script>
export default {
   data () {
    return {
      msg: 'hello world',
      hmsg: "<h1>你真的很好</h1>",
      src: 'https://www.baidu.com/img/flexible/logo/pc/result.png',
      divtitle: '你真哈搜',
      list: ['周一', '周二', '周三'],
      list1: [
        {
          tite: 'zhouli'
        },
        {
          tite: 'zhouli1111'
        }
      ],
      list2: [
        {
          count: '中国',
          list: [
            {
              city: '深圳'
            },
            {
              city: '上海'
            }
          ]
        },
        {
          count: '美国',
          list: [
            {
              city: '纽约'
            },
            {
              city: '洛杉矶'
            }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
.msg {
  color: red;
  font-size: 30px;
}
</style>