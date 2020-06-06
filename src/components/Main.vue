<template>
  <el-container>
    <el-header class="main-header">
      <el-row :gutter="20">
        <el-col :span="3" >
          的发挥地方
        </el-col>
        <el-col :span="18">
          <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
            <el-menu-item index="1">处理中心</el-menu-item>
            <el-submenu index="2">
              <template slot="title">我的工作台</template>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
              <el-menu-item index="2-3">选项3</el-menu-item>
              <el-submenu index="2-4">
                <template slot="title">选项4</template>
                <el-menu-item index="2-4-1">选项1</el-menu-item>
                <el-menu-item index="2-4-2">选项2</el-menu-item>
                <el-menu-item index="2-4-3">选项3</el-menu-item>
              </el-submenu>
            </el-submenu>
            <el-menu-item index="3" disabled>消息中心</el-menu-item>
          </el-menu>
        </el-col>
        <el-col :span="3" >
          <el-avatar icon="el-icon-user-solid" ></el-avatar>
          <el-dropdown placement="bottom-end" >
            <span class="el-dropdown-link">
              赵明明<i class="el-icon-arrow-down el-icon--right"></i>
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>个人信息</el-dropdown-item>
              <el-dropdown-item v-on:click.native="exit">退出</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-col>

        <el-col :span="3" :offset="1">


        </el-col>
      </el-row>

      <div class="line"></div>


    </el-header>
    <el-container>
      <el-aside width="200px">
        <el-menu :default-openeds="['1']">
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>导航一</template>
              <el-menu-item index="1-1"><router-link  to="/user" >user</router-link></el-menu-item>
              <el-menu-item index="1-2"><router-link  to="/test" >test</router-link></el-menu-item>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title"><i class="el-icon-menu"></i>导航二</template>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i>导航三</template>
              <el-menu-item index="3-311">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
          </el-submenu>
        </el-menu>

      </el-aside>
      <el-container>
        <el-main>
          <router-view></router-view>
        </el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </el-container>
  </el-container>

</template>

<script>
export default {
    name: 'Main',
    return: {
      activeIndex: '1',
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      },
      exit(){
        this.$router.push({path:'/'})
      }
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
  .main-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }

 /* .el-aside {
    color: #333;
  }*/
</style>
