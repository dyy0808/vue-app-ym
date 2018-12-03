<template>
    <div class="product_details">
        <div class="mui-row topNav">
            <div class="mui-col-xs-1">
                <img src="../img/icon05.png" @click="goTo">
            </div>
            <div class="mui-col-xs-10"><h3>横版珠宝标签</h3></div>
            <div class="mui-col-xs-1">
                <img src="../img/icon08.png">
            </div>
        </div>
       <div class="sBanner">
            <mt-swipe :auto="4000">
                <mt-swipe-item><img src="../img/s1.png"></mt-swipe-item>
                <mt-swipe-item><img src="../img/s2.png"></mt-swipe-item>
                <mt-swipe-item><img src="../img/s3.png"></mt-swipe-item>
            </mt-swipe>
       </div>
       <div class="collect">
           <div class="mui-row">
               <div class="mui-col-xs-4">
                   <p>已售</p>
                   <span>0</span>
               </div>
               <div class="mui-col-xs-4">
                   <p>收藏</p>
                  <span>0</span>
               </div>
               <div class="mui-col-xs-4">
                   <p>评论</p>
                   <span>0</span>
               </div>
           </div>
       </div>
       <div class="sTitle">
            <p>{{detailsList[0].details}}</p>
           <p class="price"><em>¥{{detailsList[0].price}}</em><span>会员价</span></p> 
       </div>
       <div class="detailsCon">
           <ul>
               <li>商品介绍</li>
               <li>买家评价</li>
               <li>同类推荐</li>
           </ul>
       </div>
       <div class="detailsBtn">
           <div class="mui-row">
               <div class="mui-col-xs-7 bg_blue">
                <span class="mui-icon-extra mui-icon-extra-cart"></span>
                   <router-link to="/cart">
                       <strong>购物车</strong>
                   </router-link>
               </div>
               <div class="mui-col-xs-5 bg_pink">
                    <span class="mui-icon-extra mui-icon-extra-heart"></span>
                   <strong>收藏</strong>
               </div>
           </div>
       </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                detailsList:[],
                pid:this.$route.query.pid
            }
        },
        methods:{
            goTo(){
                 this.$router.go(-1)
             },
            details(){
               // this.$router.push({name:"cart",params:{cartDetails:this.text}})
               var url="http://127.0.0.1:4000/details/app-details"
               this.$http.get(url+"?pid="+this.pid).then(result=>{
                   //console.log(result)
                    this.detailsList=result.body;
                    //console.log(result.body)
                     //console.log(this.detailsList)
                   
               })
            }
        },
        
        created(){
           this.details()
           
        }
    }
</script>
<style>
    .product_details{
         background-color: #f7f7f7;
         margin-bottom: 5rem;
    }
    .sBanner{
        background-color: #fff;
        text-align: center;
    }
    .sBanner .mint-swipe{
        height: 30rem;
        width: 80%;
        margin:0 auto;
    }
    .product_details .collect{
        background-color: #fff;
        padding: 1rem 0;
        text-align: center;
        margin-top: 2rem;
        font-size:2.4rem;
    }
   .collect p{
        font-size:2.4rem;
    }
    .collect span{
        display: block;
        color: #22c0ed;
    }
   .collect .col-xs-4{
       border-right: 1px solid #ddd;
   }
   .sTitle{
       margin: 2rem 0;  
       padding: 0 2rem;
   }
   .sTitle p{
    font-size: 2.5rem;
    line-height: 2.7rem;
   }
   .sTitle .price em{
       color: #ea2d93;
   }
   .sTitle .price span{
       background-color: #ea2d93;
       color: #fff;
       padding: 0.2rem;
       margin-left: 0.5rem;
   }
   .detailsCon{
       background-color: #fff;
       font-size:2rem;
   }
   .detailsCon li{
       border-bottom:1px solid #333;
       height: 5rem;
       line-height: 5rem;
       padding-left: 1rem;
   }
   .detailsBtn{
       margin: 1rem 0;
       color:#fff;
       text-align: center;
   }
    .detailsBtn .mui-col-xs-7,
    .detailsBtn .mui-col-xs-5{
        height:5rem;
        font-size: 2rem;
    }
    .detailsBtn .mui-icon-extra {
        font-size: 37px;
        line-height: 1.5
    }
</style>
