<template>
  <div class="login">
    <!-- el-form  表单组件 -->
    <!-- :model="form"  form对象用来收集表单中所有的数据 -->
    <!-- label-width  设置label的宽度 -->
    <!-- el-form-item 表单项 -->
  <el-form :model="form" label-width="80px">
    <img src="../assets/1.jpg" alt="">
    <el-form-item label="用户名">
      <el-input v-model="form.username" placeholder="请输入用户名"></el-input>
    </el-form-item>
    <el-form-item label="密码">
      <el-input v-model="form.password" placeholder="请输入密码"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary">登录</el-button>
      <el-button>重置</el-button>
  </el-form-item>
</el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        username: '',
        password: ''
      }
    }
  }
}
</script>

<style lang="less">
// vue 脚手架配置了less的配置  但是没有安装less和less-loader  需要我们手动安装
.login {
  height: 100%;
  background-color: #2d434c;

  .el-form {
    width: 400px;
    margin: 200px auto;
    background-color: #fff;
    padding: 75px 40px 15px;
    border-radius: 20px;
    position: relative;

    img {
      position: absolute;
      top: -70px;
      left: 50%;
      transform: translateX(-50%);
      border-radius: 50%;
      border: 10px solid #fff;
      width: 100px;
      height: 100px;
    }

    .el-button:nth-child(2) {
      margin-left: 50px;
    }
  }
}
</style>
