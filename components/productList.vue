<template>
    <div class="productList">
        <div class="mui-row topNav">
            <div class="mui-col-xs-1">
                <img src="../img/icon05.png" @click="goTo" >
            </div>
            <div class="mui-col-xs-10"><h3>商品列表</h3></div>
            <div class="mui-col-xs-1">
                <img src="../img/icon08.png">
            </div>
        </div>
        <!-- 头部结束 -->
        <div class="navMiddle">
            <div class="mui-row">
                <div class="mui-col-xs-4">价格</div>
                <div class="mui-col-xs-4">评论数</div>
                <div class="mui-col-xs-4">上架时间</div>
            </div>
        </div>
        <!-- 价格结束 -->
        <!-- 

<ul
  v-infinite-scroll="loadMore"
  infinite-scroll-disabled="loading"
  infinite-scroll-distance="10">
  <li v-for="item in list">{{ item }}</li>
</ul>
         -->
        <div class="shopList" v-infinite-scroll="loadMore"
                infinite-scroll-disabled="loading" infinite-scroll-distance="5">
            <div class="mui-row" v-for="item in lists" :key="item.pid">
    
                <div class="mui-col-xs-5">
                    <router-link :to="'/details?pid='+item.pid">
                          <img :src="'http://127.0.0.1:4000/'+item.pic">
                    </router-link>
                </div> 
                <div class="mui-col-xs-7 shopRight">
                    <router-link :to="'/details?pid='+item.pid">
                        <p>{{item.details}}</p>
                    </router-link>
                    <div>
                        会员价
                    <span class="color_pink">¥{{item.price}}</span>
                   <span @click="getShopping(item.pid)" class="listCart bg_blue mui-icon-extra mui-icon-extra-cart"></span>
                   
                    </div>
                 </div> 
                  
            </div>
            <div>到底了</div>
           
        </div>
       
    </div>
</template>
<script>
    export default{
        data(){return{
            arr1:"",
            arr2:"",
            arr3:"",
            lists:[],
           loading: false,
           page:0,
           
        }},
         methods:{
             goTo(){
                 this.$router.go(-1)
             },
            loadMore() {
                this.loading = true;
                var url1 = "pro/page";
                this.$http.get(url1+"?pno=0").then(result=>{
                    //console.log(1)
                    this.page = result.body.pageCount
                })

                var url="pro/Psearch";
                this.$http.get(url).then(result=>{
                    var id=[];
                   if(result.body.length > 0){
                       //console.log(result.body)
                       this.lists = result.body;
                       for(var item of this.lists){
                           id.push(item.pid) 
                       }
                        this.$store.commit("setId",id)
                       console.log(id)
                       this.loading = false
                   } else if(this.lists.length ==42){
                    this.loading = true
                }
                   //console.log(this.page)
                })
               
            },
            
           
             getShopping(i){
                //商品名称
                if(!localStorage.getItem("details")){
                    this.arr1=this.lists[i-1].details
                }
               else{
                    this.arr1=localStorage.getItem("details")+","+this.lists[i-1].details
                }
               localStorage.setItem("details",this.arr1)
               //商品价钱
               if(!localStorage.getItem("price")){
                   this.arr2 = this.lists[i-1].price
               }else{
                   this.arr2 = localStorage.getItem("price")+","+this.lists[i-1].price
               }
               localStorage.setItem("price",this.arr2);
               
               //商品图片 
                if(!localStorage.getItem("pic")){
                    this.arr3 = this.lists[i-1].pic
                }else{
                    this.arr3 = localStorage.getItem("pic")+","+this.lists[i-1].pic
                }
                localStorage.setItem("pic",this.arr3);

                this.$router.push("/cart")
             }
        },
        created(){
            
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
</style>
