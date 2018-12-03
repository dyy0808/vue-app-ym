<template>
    <div class="vip">
       <div class="vip-nav-top">
            <div class="mui-row">
                <div class="mui-col-xs-2">
                    <img src="../img/icon13.png">
                </div>
                <div class="mui-col-xs-8">亲爱的云马会员 欢迎回来！</div>
                <div class="mui-col-xs-2 vip-right">
                    <img src="../img/icon14.png">
                </div>
            </div>
       </div>
       <div class="vip-x-banner">
          <div class="mui-row">
               <div class="mui-col-xs-4">
               <img src="../img/ymg_peo_pic.jpg">
                </div>
                <div class="mui-col-xs-8">
                    <p>会员</p>
                    <p>{{uname}}</p>
                </div>
          </div>
       </div>
       <div class="vip-order">
           <div class="order-top">
               <div class="mui-row">
                   <div class="mui-col-xs-7">
                       <h4>我的订单</h4>
                   </div>
                   <div class="mui-col-xs-5">
                        <p>查看全部订单&nbsp;&gt;</p> 
                   </div>
               </div>
           </div>
           <div class="order-middle">
               <div class="mui-row">
                   <div class="mui-col-xs-3"><img src="../img/icon001.png"><span>待付款</span></div>
                   <div class="mui-col-xs-3"><img src="../img/icon002.png"><span>待付款</span></div>
                   <div class="mui-col-xs-3"><img src="../img/icon003.png"><span>待付款</span></div>
                   <div class="mui-col-xs-3"><img src="../img/icon004.png"><span>待付款</span></div>
               </div>
           </div>
       </div>
       <div class="vip-main">
            <div class="mui-row">
                <div class="mui-col-xs-3"><img src="../img/icon_1.png"><span>待付款</span></div>
                <div class="mui-col-xs-3"><img src="../img/icon_2.png"><span>待付款</span></div>
                <div class="mui-col-xs-3"><img src="../img/icon_3.png"><span>待付款</span></div>
                <div class="mui-col-xs-3"><img src="../img/icon_4.png"><span>待付款</span></div>
            </div>
            <div class="mui-row">
                <div class="mui-col-xs-3"><img src="../img/icon_5.png"><span>待付款</span></div>
                <div class="mui-col-xs-3"><img src="../img/icon_6.png"><span>待付款</span></div>
                <div class="mui-col-xs-3"><img src="../img/icon_7.png"><span>待付款</span></div>
                <div class="mui-col-xs-3"><img src="../img/icon_8.png"><span>待付款</span></div>
            </div>
       </div>
       <div class="vip-footer">
           <p class="color_blue">客服电话：400-987-360</p>
           <p>服务时间:星期一至五，8:30am – 5:30pm</p>
           <p class="color_blue">退出</p>
       </div>
    </div>
</template>
<script>
export default {   
    data() {  
    return {
         uname:sessionStorage.getItem("uname")
        }
    }
}
</script>
<style>
    .vip-nav-top{
        background:url(../img/head_bg.jpg);
        width: 100%;
        color:#fff;
        font-size:2rem;
        line-height: 4rem;
        padding: 0 0.2rem;
    }
    .vip-right{
        text-align: right;
    }
    .vip-nav-top img{
        width: 3rem;
        vertical-align: middle;
    }
    .vip-x-banner{
        background:url(../img/head_bg.jpg);
         width: 100%;
        height: 10rem;
        padding-top: 1.5rem;
    }
    .vip-x-banner p{
        color:#fff;
        font-size:2rem;
    }
    .vip-x-banner img{
        width: 7rem;
        border-radius:50%;
    }
    .vip-x-banner .mui-col-xs-4{
        text-align: right
    }
     .vip-x-banner .mui-col-xs-8{
         padding-left:1rem;
         margin-top:1rem;
     }
     .vip-order{
         background-color: #fff;
         padding-bottom:1rem;
     }
     .vip-order .order-top{
        padding: 1rem 0.5rem;
        border-bottom:1px solid #ddd;
     }
     .order-top .mui-col-xs-5 p{
         font-size: 1.6rem;
         text-align: right;
        
     }
     .order-middle{
         font-size:1.6rem;
         color:#666;
         text-align: center
     }
      
     .order-middle span{
         display: block
     }
     .vip-main{
         font-size:1.6rem;
         background-color: #fff;
         margin-top:1rem;
         text-align: center;
     }
     .vip-main img{
          width: 6rem;
      }
     .vip-main span{
         display: block;
     }
    .vip-main .mui-col-xs-3{
        border-left:1px solid #ddd;
        border-bottom:1px solid #ddd;
        padding: 1rem;
    }
    .vip-footer{
        margin-bottom: 3rem;
        padding: 2rem 0.5rem;
    }
    .vip-footer p{
        font-size:2rem;
        text-align: center;
    }
</style>
