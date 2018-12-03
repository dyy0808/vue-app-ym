<template>
    <div class="productList">
        <div class="mui-row topNav">
            <div class="mui-col-xs-1">
                <img src="../img/icon05.png" @click="goTo()">
            </div>
            <div class="mui-col-xs-10"><h3>购物车</h3></div>
            <div class="mui-col-xs-1">
                <img src="../img/icon08.png">
            </div>
        </div>
        <!-- 头部结束 -->
        
        <div class="shopList">
            <div class="mui-row" v-for=" (item,i) in details" :key="i">
                <div class="mui-col-xs-5">
                   <img :src="'http://127.0.0.1:4000/'+pic[i]"> 
                </div> 
                <div class="mui-col-xs-7 shopRight">
                    <p>{{item}}</p>
                    <div>
                        会员价
                        <span class="color_pink">¥{{price[i]}}</span>
                    </div>
                    <div class="cart_btn">
                        <span class="btnLeft" data-id=i @click="sub(ll[i])">-</span>
                        <input type="text" v-model="getCon[i]">
                        <span class="btnRight" data-id=i @click="add(i)">+</span>
                    </div>  
                </div> 
            </div>
        </div>
        
        <router-link tag="div" class="contaniu color_blue" to="/list">继续选择商品</router-link>
        
        <div class="total">
            <p class="hj">合计：<span class="color_pink">00.00</span></p>
            <p class="bg_blue bal">去结算</p>
        </div>
    </div>
</template>
<script>
    export default{
        data(){return{
            //cartDetails:this.$route.params.cartDetails
            //arr :[],
            details:localStorage.getItem("details").split(","),
            price:localStorage.getItem("price").split(","),
            pic:localStorage.getItem("pic").split(","),
            ll:this.$store.getters.getId,
            getCon:this.$store.getters.getId,
        }},
         methods:{
             goTo(){
                 this.$router.go(-1)
             },
              addLogin(){
                var url="http://localhost:4000/cart/shopping_cart";
                this.$http.get(url).then(result=>{
                    //console.log(result)

                })
                
            },
            add(i){
                
                console.log(i)
                this.getCon[i]++
                console.log(this.getCon[i])
            },
        },
        computed:{
            // getCon(){
            //     return this.$store.getters.getCount;//获取state里面的count
            // },
           
            
        },
        created(){
           this. addLogin()
           console.log(this.ll)
        },
    }
</script>
<style>
.productList{
    background-color: #f7f7f7;
}
.navMiddle{
    padding:1rem 1.5rem;
    background-color: #fff;
    font-size: 1.5rem;
}
.navMiddle .mui-col-xs-4{
    text-align: center;
    border-right:1px solid #ddd;
}
.navMiddle .mui-col-xs-4:last-child{
    border: none;
}
.listCart{
    color: #fff;
    border-radius: 50%;
    padding: 0.7rem;
    font-size: 3rem;
    font-weight: bolder;
}
.shopList .mui-row{
     border-top:1px solid #20c2eb;
     background-color: #fff;
     margin:1rem 0;
     padding: 1rem;

}
.shopList img{
    width: 11rem;
}
.shopRight{
    font-size: 2rem;
}
.shopRight p{
    font-size: 2rem;
    margin-bottom: 2rem;
    line-height: 2rem;
}
.cart_btn{
    margin-top:1.5rem;
    color: #fff;
    font-size: 3rem;
}
.cart_btn span{
    display: inline-block;
    width: 3rem;
    height: 3rem;
    background-color:#afaeae;
    border-radius: 5px;
    text-align: center;
    line-height: 2.3rem;
}
.cart_btn input{
    width: 4rem;
    height: 3rem;
    vertical-align: top;
    background-color: #20c2eb;
    border:none;
    text-align: center;
}
.contaniu{
    width: 14rem;
    border: 1px solid #20c2eb;
    font-size: 2rem;
    text-align: center;
    height: 4rem;
    line-height: 4rem;
    margin:0 auto 1rem;
}
.total .hj{
     height: 4rem;
    font-size:2rem;
    line-height: 4rem;
    margin-left:1rem;
}
.total .bal{
    color: #fff;
    text-align: center;
    height: 4rem;
    font-size:2rem;
    line-height: 4rem;
}

</style>
