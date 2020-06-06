<template>
  <el-container>
    <el-header>
      <el-form :inline="true" class="searchFrom"  v-model="searchForm">
        <el-row>
          <el-col :span="6">
            <el-form-item label="审批人">
              <el-input  size="small"
                         placeholder="请输入用户名"
                         prefix-icon="el-icon-s-custom"
                         v-model="searchForm.username" >
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="8">
            <el-form-item label="活动区域">
              <el-input  size="small"
                         placeholder="请输入密码"
                         prefix-icon="el-icon-search"
                         v-model="searchForm.password">
              </el-input>
            </el-form-item>
          </el-col>
          <el-col :span="4">
            <el-form-item>
              <el-button type="primary" size="small"  @click="onSubmit">查询</el-button>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" size="small"  >清空</el-button>
            </el-form-item>
          </el-col>
        </el-row>
      </el-form>
    </el-header>
    <el-main>
      <el-row>
        <el-col :span="24" style="text-align: left">
          <el-button-group >
            <el-button type="primary" size="small">删除</el-button>
            <el-button type="primary" size="small">导出</el-button>
          </el-button-group>
        </el-col>
      </el-row>
      <el-table :data="tableData" >
        <el-table-column
          type="selection"
          width="55">
        </el-table-column>
        <el-table-column prop="date" label="日期" width="140">
        </el-table-column>
        <el-table-column prop="name" label="姓名" width="120">
        </el-table-column>
        <el-table-column prop="address" label="地址">
        </el-table-column>
        <el-table-column
          fixed="right"
          label="操作"
          width="100">
          <template slot-scope="scope">
            <el-button @click="showDetail(scope.row)" type="text" size="small">查看</el-button>
            <el-button type="text" size="small">编辑</el-button>
          </template>
        </el-table-column>
      </el-table>


      <el-dialog title="收货地址" :visible.sync="dialogUserVisible">
        <el-form :model="form">
          <el-form-item label="活动名称" :label-width="formLabelWidth">
            <el-input v-model="form.date" autocomplete="off"></el-input>
          </el-form-item>
          <el-form-item label="活动区域" :label-width="formLabelWidth">
            <el-input v-model="form.name" autocomplete="off"></el-input>
          </el-form-item>
          <el-form-item label="活动区域" :label-width="formLabelWidth">
            <el-input v-model="form.address" autocomplete="off"></el-input>
          </el-form-item>
        </el-form>
        <div slot="footer" class="dialog-footer">
          <el-button @click="dialogUserVisible = false">取 消</el-button>
          <el-button type="primary" @click="dialogUserVisible = false">确 定</el-button>
        </div>
      </el-dialog>
    </el-main>
  </el-container>
</template>

<script>
export default {
    name: 'User',
    data() {
      return {
        tableData: [{
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }],
        searchForm: {
          username: '',
          password: ''
        },
        dialogUserVisible: false,
        form: {
          date: '',
          name: '',
          address: '',
        },
      }
    },
    methods: {
      handleClick(row) {
        alert(row);
      },
      showDetail(obj){
        console.log(obj);
        this.form=obj;
        this.dialogUserVisible = true;
      }
   }
  };
</script>
  .searchFrom{

  }
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >

</style>
