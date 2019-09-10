<template>
  <div class="page-register">
    <header>
      <nuxt-link to="/">
        <img src="/img/logo.png" alt="美团网">
      </nuxt-link>
      <div>
        <span>已有美团账号?</span>
        <nuxt-link to="/login">登录</nuxt-link>
      </div>
    </header>
    <main>
      <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm">
        <el-form-item label-width="100px" label="手机号" prop="phone" class="phone">
          <el-input v-model="ruleForm.phone" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label-width="100px" label="短信动态码" prop="mes" class="mes">
          <button class="getMes">免费获取短信动态码</button>
          <el-input v-model="ruleForm.mes" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label-width="100px" label="密码" prop="pass">
          <el-input type="password" v-model="ruleForm.pass" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label-width="100px" label="确认密码" prop="checkPass">
          <el-input type="password" v-model="ruleForm.checkPass" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label-width="100px" class="register">
          <el-button type="primary" @click="submitForm('ruleForm')">同意以下协议并注册</el-button>
          <div class="agreement">
            <nuxt-link to="/agreement">《美团网用户协议》</nuxt-link>
          </div>
        </el-form-item>
      </el-form>
    </main>
  </div>
</template>

<script>
  export default {
    name: 'register',
    layout: 'blank',
    head() {
      return {
        title: '注册 | 美团网'
      }
    },
    data() {
      var validatePhone = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请输入您的手机号码'))
        } else if (!/^\d{11}$/.test(value)) {
          callback(new Error('请输入正确的11位手机号码'))
        } else {
          callback()
        }
      }
      var validateMes = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请输入短信动态码'))
        } else {
          callback()
        }
      }
      var validatePass = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请输入密码'))
        } else if (value.length < 8) {
          callback(new Error('密码太短，至少8个字符'))
        } else if (value.length > 32) {
          callback(new Error('密码太长，最多32个字符'))
        } else {
          if (this.ruleForm.checkPass !== '') {
            this.$refs.ruleForm.validateField('checkPass')
          }
          callback()
        }
      }
      var validatePass2 = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请再次输入密码'))
        } else if (value !== this.ruleForm.pass) {
          callback(new Error('两次输入密码不一致!'))
        } else {
          callback()
        }
      }
      return {
        ruleForm: {
          phone: '',
          pass: '',
          checkPass: '',
          mes: ''
        },
        rules: {
          phone: [
            { validator: validatePhone, trigger: 'blur' }
          ],
          mes: [
            { validator: validateMes, trigger: 'blur' }
          ],
          pass: [
            { validator: validatePass, trigger: 'blur' }
          ],
          checkPass: [
            { validator: validatePass2, trigger: 'blur' }
          ]
        }
      }
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!')
          } else {
            console.log('error submit!!')
            return false
          }
        })
      },
      resetForm(formName) {
        this.$refs[formName].resetFields()
      }
    }
  }
</script>

<style scoped lang="scss">

  .page-register {
    header {
      border-bottom: 2px solid #D8D8D8;
      display: flex;
      justify-content: space-between;
      padding: 10px 142px;
      align-items: center;

      img {
        height: 36px;
      }

      div {
        display: flex;
        align-items: center;

        span {
          margin-right: 16px;
          font-size: 14px;
          color: #666;
        }

        a {
          background-color: rgb(255, 194, 0);
          padding: 4px 12px;
          font-size: 12px;
          border-radius: 2px;
          box-shadow: 1px 1px 2px rgba(0, 0, 0, .2);
        }
      }
    }

    main {
      margin: 30px 142px 0;

      .el-form {
        padding: 8px 0 8px 20px;

        .el-form-item {

          &.register {

            .el-button {
              background-color: rgb(255, 192, 0);
              padding: 10px 20px;
              border: none;
              color: rgb(32, 32, 32);
              font-weight: bold;
              border-radius: 2px;
              box-shadow: 0 1px 2px rgba(0, 0, 0, .2);
            }
          }

          &.mes {
            position: relative;

            .getMes {
              height: 21px;
              padding: 1px 8px 0;
              border-radius: 2px;
              line-height: 21px;
              position: absolute;
              top: -29px;
              font-size: 12px;
              left: 0;
              color: #333;
              background-color: #dedede;
              border: 1px solid #e3e3e3;
              border-bottom: 1px solid #aaa;
              cursor: pointer;
              background-image: linear-gradient(to bottom,#f7f7f7,#dedede);
              &:hover{
                background-image: linear-gradient(to bottom,#fff,#e9e9e9);
              }
              &:active{
                background-image: linear-gradient(to bottom,#ddd,#eee);
              }
            }
          }
          &.phone{
            padding-bottom: 16px;
          }

          .el-input {
            width: 260px;

            input {
              padding: 5px;
            }
          }
        }

      }

      a {
        color: #FE8C00;
        font-size: 13px;
      }
    }
  }

</style>