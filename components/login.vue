<template>
    <div class="login">
        <div class="mui-row topNav">
            <div class="mui-col-xs-1">
                <img src="../img/icon05.png">
            </div>
            <div class="mui-col-xs-11"><h3>会员登录</h3></div>
        </div>
        <!-- 头部结束 -->
        <form class="login_inp">
            <div class="mui-row">
                <div class="mui-col-xs-2">
                    <label class="mui-icon mui-icon-person"></label>
                </div>
                <div class="mui-col-xs-10">
                    <input v-model="uname" type="text" placeholder="请输入手机/邮箱">
                </div>
            </div>
            <div class="mui-row">
                <div class="mui-col-xs-2">
                    <label class="mui-icon mui-icon-locked"></label>
                </div>
                <div class="mui-col-xs-10">
                    <input type="password" v-model="upwd" placeholder="请输入密码">
                </div>
            </div>
            <div class="hint">
                <div class="mui-row">
                    <div class="mui-col-xs-5">
                        <input type="radio">
                        <span class="remember color_blue">记住我</span>
                    </div>
                      <div class="mui-col-xs-7">
                       <a class="forget color_blue">忘记密码？</a>
                    </div>
                </div> 
            </div>
            <button class="bg_blue" @click.prevent="isLogin()">登录</button>
        </form>
       <p class="out">还不是会员？你out啦！<span class="color_blue">点这里，立即注册</span></p>
    </div>
</template>
<script>
import { Toast } from 'mint-ui';
    export default{
        data(){return{
            uname:"",
            upwd:"",
        }},
        methods:{
            isLogin(){
               //console.log(11)
               //console.log(this.uname)
                var url="http://localhost:4000/user/isignn";
                
                this.$http.post(url,{uname:this.uname,upwd:this.upwd}).then(result=>{
                    //console.log(result)
                   if(result.body.ok==1){
                       Toast("登录成功")
                       sessionStorage.setItem("uname",this.uname)
                       sessionStorage.setItem("userName","退出")
                       this.$router.push("/vip")

                   }else if(result.body.ok==0){
                       Toast("登录失败")
                   }
                    //console.log(result.body)
                })
            },
        },
        created(){
            
        },
    }
</script>
<style>
.login{
    font-size: 2rem;
}
.login .topNav{
    background-color: #f7f7f7;
}
.login_inp>.mui-row {
    background-color: #fff;
    border-bottom: 1px solid #999;
    padding-top: 0.7rem;
    text-align: center;
   
}
.login_inp label{
 font-size: 4rem;
}
.login_inp input{
    border:none;
    outline: none;
}
.hint{
    font-size: 2rem;
    padding: 2rem 1rem;
}
.hint .forget{
    text-align: right;
}
.hint .mui-col-xs-7{
    text-align: right
}
.login_inp button{
    width: 100%;
    color: #fff;
    padding: 1rem 0;
    font-size: 2rem;
}
.login .out {
    font-size: 2rem;
    margin: 2rem 0;
   text-align: center;
}
</style>
