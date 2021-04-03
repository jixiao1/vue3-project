<template>
  <div class="inputForm">
    <h1>人员表单</h1>
    <div>
      <label for="">姓名:</label>
      <input type="text" v-model="userInfo.name">
    </div>
    <div>
      <label for="">年龄:</label>
      <input type="text" v-model="userInfo.age">
    </div>
    <div class="sex">
      性别:
      <input type="radio" value="1" name="sex" v-model="userInfo.sex"><label for="sex">男</label>
       <input type="radio" value="2" name="sex" v-model="userInfo.sex"><label for="sex">女</label>
    </div>
    <div style="margin-left: -120px; ">
      城市：
      <select v-model="userInfo.city">
        <option v-for="(item,index) in userInfo.cityList" :key="index" :value="item">{{item}}</option>
      </select>
    </div>
    <div class="hobby">
      爱好
      <span v-for="(item ,index) in userInfo.hobby" :key="index">
        <input type="checkbox" class="chengkl" v-model="item.checked">
        <label for="item">{{item.title}}</label>
      </span>
    </div>
    <div class="text">
      文本域：
      <textarea v-model="userInfo.mark" placeholder="请输入你的信息"></textarea>
    </div>
    <div class="submit">
      <button @click="submit">提交</button>
    </div>
    <pre>
      {{userInfo}}
    </pre>
  </div>
</template>

<script>
export default {
  data () {
    return {
      userInfo: {
        name: '',
        age: '',
        sex: "1",
        cityList: ['北京', '上海', '广州'],
        city: '北京',
        hobby: [
          {
            title: '吃饭',
            checked: true
          },
          {
            title: '睡觉',
            checked: false
          },
          {
            title: '打豆豆',
            checked: false
          }
        ],
        mark: ''
      }
    }
  },
  methods: {
    submit () {
      console.log(this.userInfo)
    }
  }
}
</script>

<style lang="scss" scoped>
.inputForm {
  width: 550px;
 padding: 20px;
  border: 5px solid red;
  position: absolute;
  left: 550px;
  top: 300px;
  h1 {
    margin: 10px auto;
    text-align: center;
  }
  >div {
    margin: 20px auto;
    width: 100%;
    height: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    label {
      margin-right: 20px;
    }
    >input {
      width: 300px;
      height: 30px;
    }
  }
  .sex {
    width: 500px;
    >input {
      width: 100px;
      height: 30px;
    }
    select {
      width: 200px;
      height: 30px;
    }
  }
  .hobby {
    input {
      width: 10px;
      height: 10px;
    }
  }
  .text {
    textarea {
      // height: 400px;
    }
  }
}
</style>