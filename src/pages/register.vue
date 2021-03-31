<template>
    <div class="register">
        <div class="container">
            <div class="logo">
                <a href="/#/index"><img src="/imgs/mi-logo.png" alt=""></a>
            </div>
            <div class="register-form">
                <h3>注册小米账号</h3>
                <p>账号</p>
                <div class="input">
                    <input type="text" placeholder="请输入账号" v-model="username">
                </div>
                <p>密码</p>
                <div class="input">
                    <input type="password" placeholder="请输入密码" v-model="password">
                </div>
                <p>确认密码</p>
                <div class="input">
                    <input type="password" placeholder="请再次输入密码">
                </div>
                <div class="btn-box">
                    <button class="btn" @click="register">注册账号</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'register',
    data(){
        return {
            username: '',
            password: '',
        }
    },
    methods: {
    register(){
      this.axios.post('/user/register',{
        username:'admin1',
        password:'admin1',
        email:'admin1@163.com'
      }).then(()=>{
        this.$message.success('注册成功');
      })
    }
    }
}
</script>

<style lang="scss" scoped>
 @import './../assets/scss/config.scss';
 .container{
     display: flex;
     flex-direction: column;
     width: 400px;
     margin-top: 200px;
     padding: 20px 0px;
     border: 1px solid grey;
     border-radius: 2%;
     box-shadow:0px 0px 4px grey;
     .logo{
        background-color: $colorA;
        width: 50px;
        height: 50px;
        margin: 0 auto;
        border-radius: 2px;
    }
    .register-form{
        margin:20px auto;
        h3{
            font-size: $fontC;
            text-align: center;
            margin-bottom: 40px;
        }
        p{
            margin-bottom: 6px;
        }
        .input{      
            width:280px;
            height:38px;
            margin-bottom:10px;
        }
        input{
            width: 100%;
            height: 100%;
            border:1px solid #E5E5E5;
            padding-left:10px;
          }
        .btn-box{
            margin-top:30px;
            text-align: center;
            button{
                width: 290px;
                height: 38px;
            }
        }
    }
 }
    
</style>