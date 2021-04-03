## vue3 搭建项目
搭建Vue3.0的项目，
必须依赖 Vue-cli 3.0 或者以上的版本，打开命令窗口，通过以下命令进行安装和查看版本号：

  // 安装最新版的vue-cli
  npm install -g @vue/cli  
  // 查看版本号
  vue -V  

### 通过vue-cli创建项目

1.vue create my-app
2.npm serve

## 通过vite 脚手架创建项目
  ### 1. 使用npm创建项目

  1.1 npm init vite-app <projet-name>
  1.2 cd <project-name>
  1.3 npm install
  1.4 npm run dev

  ### 2.使用yarn创建项目
    1. yarn create vite-app <project-name>
    2. cd <project-name>
    3. yarn
    4.yarn dev

  ## 遍历数组

  1. 普通数组
  <li v-for="(item, index) in list" :key="index">
            {{item}}
  </li>

  list: ['周一', '周二', '周三']

  2. 数组对象
  <li v-for="(item ,index) in list1" :key="index">
             {{item.tite}}
   </li>

  list1: [
      {
        tite: 'zhouli'
      },
      {
        tite: 'zhouli1111'
      }
    ],

    3. 数组对象嵌套数组、
  <div v-for="(item, index) in list2" :key="index">
      <span>
        {{item.count}}^
        <div v-for="(item1, index1) in item.list" :key="index1">
          <span style="color: red;">{{item1.city}}</span>
        </div>
      </span>
    </div>

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
## vue3 中事件方法入门，模板语法模板类名的绑定


## 取消默认事件

 1.w3c的方法是e.preventDefault()，

 2.IE则是使用e.returnValue = false;

 ## 事件修饰符
 为了解决这个问题，Vue.js 为 v-on 提供了事件修饰符。之前提过，修饰符是由点开头的指令后缀来表示的。

.stop
.prevent
.capture
.self
.once
.passive
<!-- 阻止单击事件继续传播 -->
<a v-on:click.stop="doThis"></a>

<!-- 提交事件不再重载页面 -->
<form v-on:submit.prevent="onSubmit"></form>

<!-- 修饰符可以串联 -->
<a v-on:click.stop.prevent="doThat"></a>

<!-- 只有修饰符 -->
<form v-on:submit.prevent></form>

<!-- 添加事件监听器时使用事件捕获模式 -->
<!-- 即内部元素触发的事件先在此处理，然后才交由内部元素进行处理 -->
<div v-on:click.capture="doThis">...</div>

<!-- 只当在 event.target 是当前元素自身时触发处理函数 -->
<!-- 即事件不是从内部元素触发的 -->
<div v-on:click.self="doThat">...</div>

## 表单绑定
  ### 单选框
<div class="sex">
      性别:
      <input type="radio" value="1" name="sex" v-model="userInfo.sex"><label for="sex">男</label>
       <input type="radio" value="2" name="sex" v-model="userInfo.sex"><label for="sex">女</label>
 </div>

### 下拉框
  <div style="margin-left: -120px; ">
      城市：
      <select v-model="userInfo.city">
        <option v-for="(item,index) in userInfo.cityList" :key="index" :value="item">{{item}}</option>
      </select>
    </div>

    
### 多选框
<div class="hobby">
      爱好
      <span v-for="(item ,index) in userInfo.hobby" :key="index">
        <input type="checkbox" class="chengkl" v-model="item.checked">
        <label for="item">{{item.title}}</label>
      </span>
    </div>


  