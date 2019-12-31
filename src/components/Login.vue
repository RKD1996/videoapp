<template>
  <div class="login">
    <div align="center">
  <b-card title="Login" style="max-width: 25rem;" class="mb-2 mt-5">
    <b-card-text>
      <b-form-input type="email" placeholder="Email (example@example.com)" v-model="user.username"></b-form-input>
      <span v-if="isEmail">Not an Email</span>
      <div class="password">
        <b-form-input :type="input_type" placeholder="Password (minimum 6 characters)" v-model="user.password_digest"></b-form-input>
        <i class="material-icons" v-if="visibility" @click="showPassword()">visibility</i>
        <i class="material-icons" v-else @click="showPassword()">visibility_off</i>
      </div>
      <span v-if="pass_match">password length is less than 6</span>
    </b-card-text>
    <b-button variant="primary" @click="submit()">login</b-button>
  </b-card>
</div>
  </div>
</template>
<script>
import axios from 'axios'

  export default {
    name: 'login',
    data ( ) {
      return {
          isEmail: false,
          pass_match: false,
          input_type: 'password',
          visibility: false,
          user: {
            useranme: '',
            password: ''
          }
      }
    },
    methods: {
      showPassword () {
        this.visibility = !this.visibility
        this.input_type = this.visibility? 'text':'password'
      },
      submit () {
        this.isEmail = (this.user.username.match('@') && this.user.username != '')? true:false
        console.log(this.isEmail)
        console.log(this.user.password_digest.length )
        if (this.user.password_digest.length >= 6 && this.isEmail) {
          this.isEmail = false
          let vm = this
          axios({
            method: 'post',
            url: 'http://localhost:3000/users/login',
            data: {
              'username': vm.user.username,
              'password_digest': vm.user.password_digest
            }
          }).then(function (res) {
            vm.$router.push('/')
          }).cath(function (err) {
            alert('Email or Password is wrong')
          })
        } else  if (this.user.password_digest.length < 6) {
            this.pass_match = true
        } else if (!this.isEmail) {
          this.isEmail = true
        }
      }
    }
  }
</script>
<style lang="scss" scoped>
  .login{
    input{
      margin-top: 5px;
    }
    .password {
      display: flex;
      align-items: center;
      i{
        margin-left: -30px;
      }
    }
  }
</style>
