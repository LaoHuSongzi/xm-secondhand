<template>
  <div class="container">
    <div class="bg" style="flex: 1; ">
      <div style="height: calc(100vh - 50px); display: flex; align-items: center; justify-content: center">
        <div style="width: 400px; padding: 40px; border-radius: 5px;">
          <div style="height: 50px; display: flex; align-items: center; padding-left: 30px; margin-bottom: 20px">
            <img src="@/assets/imgs/logo1.png" alt="" style="width: 40px">
            <span style="font-size: 20px; margin-left: 25px;color: aliceblue">校园二手交易平台</span>
          </div>
          <el-form :model="form" :rules="rules" ref="formRef">
            <el-form-item prop="username">
              <el-input size="medium" prefix-icon="el-icon-user" placeholder="请输入账号" v-model="form.username"></el-input>
            </el-form-item>
            <el-form-item prop="password">
              <el-input size="medium" prefix-icon="el-icon-lock" placeholder="请输入密码" show-password  v-model="form.password"></el-input>
            </el-form-item>
            <el-form-item prop="role">
              <el-select v-model="form.role" style="width: 100%">
                <el-option label="管理员" value="ADMIN"></el-option>
                <el-option label="用户" value="USER"></el-option>
              </el-select>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" plain size="medium" style="width: 100%; " @click="login">登 录</el-button>
            </el-form-item>
          </el-form>
          <div style="display: flex; margin-bottom: 50px; font-size: 12px" >
            <span style="margin-left: 70px">如果您还没有账号，请先</span><a style="color: cornflowerblue" href="/register"><div style="margin-left: 2px;">注册</div></a>
          </div>
        </div>
      </div>

    </div>


  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      form: { role: 'ADMIN' },
      rules: {
        username: [
          { required: true, message: '请输入账号', trigger: 'blur' },
        ],
        password: [
          { required: true, message: '请输入密码', trigger: 'blur' },
        ]
      }
    }
  },
  created() {

  },
  methods: {
    login() {
      this.$refs['formRef'].validate((valid) => {
        if (valid) {
          // 验证通过
          this.$request.post('/login', this.form).then(res => {
            if (res.code === '200') {
              localStorage.setItem("xm-user", JSON.stringify(res.data))  // 存储用户数据
              if (res.data.role === 'ADMIN') {
                this.$router.push('/home')  // 跳转主页
              } else {
                this.$router.push('/front/home')  // 跳转主页
              }
              this.$message.success('登录成功')
            } else {
              this.$message.error(res.msg)
            }
          })
        }
      })
    }
  }
}
</script>

<style scoped>
.container {
  height: 100vh;
  overflow: hidden;
  display: flex;
}
a {
  color: #2a60c9;
}
.bg{
  background: url("../assets/imgs/bg.png") no-repeat ;
  background-size:cover ;
}
</style>