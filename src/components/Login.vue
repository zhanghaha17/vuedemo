<template>
  <div>
    <el-form ref="form" :model="form" label-width="80px">
      <el-form-item label="用户名">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input type="password" v-model="form.password"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">登录</el-button>
      </el-form-item>
    </el-form>

<!--    <el-table
      :data="tableRes"
      style="width: 100%">
      <el-table-column
        prop="id"
        label="主键"
        width="180">
      </el-table-column>
      <el-table-column
        prop="username"
        label="姓名"
        width="180">
      </el-table-column>
      <el-table-column
        prop="age"
        label="年龄">
      </el-table-column>
    </el-table>-->
  </div>


</template>

<script>
export default {
  name: "Login",
  data(){
    return{
      form:{
        name:'',
        password:''
      },
      tableRes:[]
    }
  },
  methods:{
    onSubmit(){
      // this.$axios.get('/user/queryAllUser')
      //   .then(value => {
      //     this.tableRes = value.data.data;
      //     console.log(value);
      //   }).catch(error => {
      //
      // });

      this.$axios.post('api/web/user/login',
        {
          username: this.form.name,
          password: this.form.password
        }).then(value => {
           this.$router.push("./index");
        }).catch(error => {
           this.$message(error.response.data.message);
        })
    }
  }
}
</script>

<style scoped>

</style>
