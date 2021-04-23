<template>
  <div class="login-wrap">
    <el-form
      class="login-form"
      label-position="top"
      label-width="80px"
      :model="formdata"
    >
      <h2>用户登录</h2>
      <el-form-item label="用户名">
        <el-input v-model="formdata.username"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="formdata.password"></el-input>
      </el-form-item>
      <el-button class="login-btn" type="primary" @click="handleLodin()">登录</el-button>
    </el-form>
  </div>
</template>
<script>
export default {
  name: "Login",
  data() {
    return {
      formdata: {
        username: "",
        password: "",
      },
    };
  },
  methods: {
    handleLodin() {
      //测试版本
      if (this.formdata.username !== '' && this.formdata.password !== '') {
        this.$router.push({path: '/home'})
        //  2.提示成功
        this.$message({
          showClose: true,
          message: '登录成功',
          type: 'success'
        });
      } else {
        this.$message({
          showClose: true,
          message: '用户名和密码不能为空',
          type: 'error'
        });
      }
    }
  }
};

</script>
<style scoped>
.login-wrap {
  height: 100%;
  background: #324152;
  display: flex;
  justify-content: center;
  align-items: center;
}

.login-form {
  width: 400px;
  background: #fff;
  border-radius: 5px;
  padding: 30px;
}

.login-btn {
  width: 100%;
}
</style>
