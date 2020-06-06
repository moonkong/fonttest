<template>
  <div class="hello">
    <Form v-model="loginForm" >
      <input v-model="loginForm.username" :rules="rulesLogin" placeholder="请输入用户名"><br>
      <input v-model="loginForm.password" :rules="rulesLogin" placeholder="请输入密码"><br>
      <button v-on:click="login">登录</button>
    </Form>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      loginForm: {
        username: '',
        password: ''
      },
      rulesLogin:{ // 校验表单规则
        username: [ // FormItem标签中的 prop 属性预期值
          { required: true, message: '用户名不能为空', trigger: 'blur' }
        ],
          password: [ // FormItem标签中的 prop 属性预期值
          { required: true, message: '密码不能为空', trigger: 'blur' },
          { type: 'string', min: 6, message: '6位数密码', trigger: 'blur' }
        ]
      }
    }
  },
  // 在 `methods` 对象中定义方法
  methods: {
    login: function () {
      this.$router.push({path:'/main'})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
