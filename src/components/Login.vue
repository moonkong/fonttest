<template>
  <div class="hello">
    <el-container>
      <el-header></el-header>
      <el-main>
        <el-row :gutter="20">
          <el-col :span="8" :offset="8">
          <el-form class="login-container"  v-model="loginForm">
              <el-row class="tole">
                  <h3>xx系统</h3>
              </el-row>
              <el-row :gutter="20" class="rows-st">
                <el-col :span="16" :offset="4">
                  <el-input  size="small"
                            placeholder="请输入用户名"
                    prefix-icon="el-icon-s-custom"
                    v-model="loginForm.username" >
                  </el-input>
                </el-col>
              </el-row>
              <el-row :gutter="20" class="rows-st">
                <el-col :span="16" :offset="4">
                  <el-input  size="small"
                            placeholder="请输入密码"
                    prefix-icon="el-icon-search"
                    v-model="loginForm.password">
                  </el-input>
                </el-col>
              </el-row>
            <el-row :gutter="20" class="rows-st rows-st-bu">
              <el-col :span="16" :offset="4">
                <el-button type="primary" size="small" style="width: 100%" v-on:click="login">登录</el-button>
              </el-col>
            </el-row>
          </el-form>
            </el-col>

        </el-row>


      </el-main>
      <el-footer></el-footer>
    </el-container>
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
<style >
  .el-header, .el-footer {
    text-align: center;
  }

  .tole{
    background-color: darkgrey;
  }

  .login-container{
    background-color: #B3C0D1;
    color: #333;
  }

  .rows-st{
    margin-top: 40px;
  }

  .rows-st-bu{
    padding-bottom: 20px;
  }

  .el-main {
    text-align: center;

  }


</style>
