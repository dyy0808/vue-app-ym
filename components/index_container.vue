<template>
<div class="index_container">
  <!--头部-->
<div class="app_header" >
        <div class="mui-row">
            <div class="mui-col-xs-4 logo"><img src="../img/logo.jpg" alt=""></div>
            <div class="mui-col-xs-6 search"><input type="text"></div>
            <div class="mui-col-xs-2 login">
              
                 <img src="../img/icon02.jpg" alt="">
                 <p v-if="userName" @click="close">{{userName}}</p>
                 <p v-else>未登录</p>
             
            </div>
        </div>
    </div>
<!--头部结束-->
      <div class="navPic mui-content">
        <ul class="mui-table-view mui-grid-view mui-grid-9">
            <li v-for="list in imgList" class="mui-table-view-cell mui-media mui-col-xs-3 mui-col-sm-3"><a href="#">
                  <!-- <span><img src="../img/icon01.png"></span> -->
                  <img :src="list.img">
                  <div class="mui-media-body">{{list.name}}</div></a>
            </li>
        </ul> 
		</div>
     <!--  -->
     <div class="mui-row top_nav lineHeight">
        <div class="nav_img mui-col-xs-4 mui-col-sm-4">
            <img src="../img/icon03.jpg">
        </div>
         <div class="mui-col-xs-8 mui-col-sm-8">
           <span>2018世界印刷与传播论坛大会！</span>
        </div>
     </div>
     <!-- 标签产品 -->
     <div class="main_01">
        <div class="nav">
          <mt-button size="small" @click.native.prevent="active = 'tab-container1'">空白标签</mt-button>
          <mt-button size="small" @click.native.prevent="active = 'tab-container2'">A4标签</mt-button>
        </div>
        <div class="page-tab-container">
          <mt-tab-container class="page-tabbar-tab-container" v-model="active" swipeable>
            <mt-tab-container-item id="tab-container1">
              <!-- tab01 -->
                <div class="mui-row top_nav">
                  <div class="top_nav_con mui-col-xs-4 mui-col-sm-4" v-for="item in product_01">
                    <router-link to="/list">
                      <img :src="'http://127.0.0.1:4000/'+item.pic">
                      <p>{{item.details}}</p>
                      <span class="recommend">推荐</span>
                      <em class="price">¥{{item.price}}</em>
                    </router-link>
                  </div>
              </div>
            </mt-tab-container-item>
             <!--tab01 end  -->
              <!-- tab02 -->
            <mt-tab-container-item id="tab-container2">
              <div class="mui-row top_nav">
                  <div class="top_nav_con mui-col-xs-4 mui-col-sm-4" v-for="item in product_01">
                    <router-link to="/list">
                      <img :src="'http://127.0.0.1:4000/'+item.pic">
                      <p>{{item.details}}+qq</p>
                      <span class="recommend">推荐</span>
                      <em class="price">¥{{item.price}}</em>
                  </router-link>
                  </div>
              </div>
            </mt-tab-container-item>
          </mt-tab-container>
        </div>
        <p class="a_link">
          <router-link to="/list">
              进入商城
          </router-link>
        </p>
    </div>
     <!--打印机产品-->
   <div class="main_01">
        <div class="nav">
          <mt-button size="small" @click.native.prevent="active = 'tab-container1'">标签打印机</mt-button>
          <mt-button size="small" @click.native.prevent="active = 'tab-container2'">采集器</mt-button>
          <mt-button size="small" @click.native.prevent="active = 'tab-container3'">扫描器</mt-button>
          <mt-button size="small" @click.native.prevent="active = 'tab-container4'">碳带</mt-button>
        </div>
        <div class="page-tab-container">
          <mt-tab-container class="page-tabbar-tab-container" v-model="active" swipeable>
             <!-- tab01 -->
            <mt-tab-container-item id="tab-container1">
                <div class="mui-row top_nav">
                  <div class="top_nav_con mui-col-xs-4 mui-col-sm-4" v-for="item in product_01">
                    <router-link to="/list">
                      <img :src="'http://127.0.0.1:4000/'+item.pic">
                      <p>{{item.details}}</p>
                      <span class="recommend">推荐</span>
                      <em class="price">¥{{item.price}}</em>
                    </router-link>
                  </div>
              </div>
            </mt-tab-container-item>
             <!--tab01 end  -->
              <!-- tab02 -->
            <mt-tab-container-item id="tab-container2">
              <div class="mui-row top_nav">
                  <div class="top_nav_con mui-col-xs-4 mui-col-sm-4" v-for="item in product_01">
                    <router-link to="/list">
                      <img :src="'http://127.0.0.1:4000/'+item.pic">
                      <p>{{item.details}}+02</p>
                      <span class="recommend">推荐</span>
                      <em class="price">¥{{item.price}}</em>
                    </router-link>
                  </div>
              </div>
            </mt-tab-container-item>
             <!-- tab02 end-->
             <!-- tab03  -->
              <mt-tab-container-item id="tab-container3">
              <div class="mui-row top_nav">
                  <div class="top_nav_con mui-col-xs-4 mui-col-sm-4" v-for="item in product_01">
                    <router-link to="/list">
                      <img :src="'http://127.0.0.1:4000/'+item.pic">
                      <p>{{item.details}}+03</p>
                      <span class="recommend">推荐</span>
                      <em class="price">¥{{item.price}}</em>
                    </router-link>
                  </div>
              </div>
            </mt-tab-container-item>
             <!-- tab03 end -->
             <!-- tab04  -->
              <mt-tab-container-item id="tab-container4">
              <div class="mui-row top_nav">
                  <div class="top_nav_con mui-col-xs-4 mui-col-sm-4" v-for="item in product_01">
                    <router-link to="/list">
                      <img :src="'http://127.0.0.1:4000/'+item.pic">
                      <p>{{item.details}}+04</p>
                      <span class="recommend">推荐</span>
                      <em class="price">¥{{item.price}}</em>
                    </router-link>
                  </div>
              </div>
            </mt-tab-container-item>
             <!-- tab04 end -->
          </mt-tab-container>
        </div>
        <p class="a_link">
          <router-link to="/list">进入商城</router-link>
        </p>
    </div>
   <!--场景-->
    <div class="application">
        <div class="mui-row application_top">
            <div class="mui-col-xs-9">
              <h3 class="color_blue">
                <span> 场景应用</span>
              </h3>
            </div>
            <div class="mui-col-xs-3">
              <a href="#" class="more">更多&nbsp;&gt;</a>
          </div>
        </div>
        <div class="mui-row" v-for="item in cjImg">
            <div class="mui-col-xs-6 cjPic" v-for="item in cjImg">
                <img src="../img/ym3_pic05.jpg">
                <p>{{item.title}}</p>
            </div>
        </div>
    </div>
   <!-- 场景 end -->
   <div class="footerNav">
        <div class="mui-row">
            <div class="mui-col-xs-4 cjPic" v-for="item in footerNav">
                <h4>{{item.name}}</h4>
                <p>{{item.deal}}</p>
            </div>
        </div>
    </div>
  <!---->
   </div>
</template>
<script>
export default { 
  name: 'page-tab-container',  
  data() {  
    return {  
      userName:sessionStorage.getItem("userName"),
      active: 'tab-container1',
      imgList:[
        {img:"http://localhost:4000/image/icon01.png",name:"LS软件"},
        {img:"http://localhost:4000/image/icon02.png",name:"云马商城"},
        {img:"http://localhost:4000/image/icon03.png",name:"应用方案"},
        {img:"http://localhost:4000/image/icon04.png",name:"服务支持"},
      ],
      product_01:[],
      product_02:[],
      cjImg:[{name:1,title:"企业标签"},{name:2,title:"办公标签"}],
      footerNav:[
          {name:"设备问题",deal:"Equipment"},
          {name:"打印问题",deal:"Print issue"},
          {name:"标签问题",deal:"Label problem"},
        ],
      }
  },
  methods:{
      close(){
        sessionStorage.clear();
        console.log(this.userName)
        //localStorage.clear();
        this.$router.push("/login");
      },
      getTagImg(){
         // var url = "http://127.0.0.1:5000/getImg";
        //  var pid=this.pid
         var url = "http://127.0.0.1:4000/pro/product";
          this.$http.get(url).then(result=>{
            this.product_01=result.body.splice(0,6)
            //console.log(this.product_01)
          })
      },
      getComImg(){
        var url="http://127.0.0.1:4000/pro/product";
        this.$http.get(url).then(result=>{
          this.product_02=result.body.splice(5,8)
          //console.log(this.product_02)
        })
      },
  },
  created() {
    this.getTagImg();
    this.getComImg();
  },


};  
</script>
<style>
  /* 头部 scoped*/
   .app_header{
        position: fixed;
        z-index: 1;
        background-color: #f7f7f7;
        width: 100%;
        /* padding: 12px 0; */
        font-size: 1rem !important;
        padding-top:1rem;
    }
    .app_header .mui-row > [class*='mui-col-'] {
        text-align: center;
    }
    .app_header .search input{
        /* width: 100%; */
        height: 2.7rem;
    }
    .app_header img{
        vertical-align: middle
    }
    .header_top img{
        vertical-align: middle;
    }
    .logo img{
        width: 8rem; 
    }
    .login img{
        width: 2.2rem; 
    }
  /* 头部 end */
  .recommend{
    display: inline-block;
    color: #ea2d93;
    font-size:0.7rem;
    border:1px solid #ea2d93;
    padding: 0 0.4rem;
  }
  .a_link{
    width: 8rem;
    /* margin: 2rem auto; */
    padding: 0.5rem 1rem;
    border:1px solid #666;
    text-align: center;
    margin:3rem auto 0;
  }

  .index_container{
    overflow: hidden;
  }
  .index_container .mui-content ul li img{
    width: 5rem;
  }
  .index_container .top_nav{
      font-size: 1.5rem;
      overflow: hidden;
      background-color: #fff;
      
  }
  .navPic{
    margin-top:5rem;
  }
  .lineHeight{
    line-height: 4rem;
  }
  .main_01{
    background-color: #fff;
    margin-top:1rem;
    padding-bottom: 2rem;
  }
   .main_01 .page-tab-container{
     margin-top:15px;
     text-align: center;
   }
  .main_01 .nav{
      padding: 10px 0;
      border-bottom: 1px solid #ddd;
  }
  .top_nav_con{
    border-right: 1px solid #ddd;
  }
  .top_nav_con em{
    display: block;
     color:  #ea2d93;
  }
  .main_01 .nav button{
    background: #fff;
    border: 0;
    box-shadow: none;
    font-size: 2rem;
    color: #22c0ed;
  }
  .index_container .top_nav .mui-row > [class*='mui-col-']{
    text-align: center
  }
  .index_container .top_nav img{
    width: 8rem;
    vertical-align: middle;
    border-right: 1px solid #ddd;
  } 
   .index_container .top_nav p{
    font-size: 1rem;
    width: 8rem;
    text-align: left;
    margin:0 auto;
  }
  .nav_img{
    padding: 0 8px;
  }
  /* 场景 */
  .application{
    margin-top:1rem;
    background-color: #fff;
    line-height: 2rem;
  }
   .application h3{
     padding-left: 1rem;
     margin-bottom:1rem;
   }
  .application h3 span::before{
    content: "";
    display: inline-block;
    width: 0.5rem;
    height: 3rem;
    background:#22c0ed;
    vertical-align: middle;
  }
.more{
  font-size: 1.5rem;
  color: #333;
}
  .cjPic{
    padding: 0 1rem;
    text-align: center;
  }
  .cjPic img{
    width: 100%;
  }
  /* footerNav */
  .footerNav{
    margin:1rem 0 5rem;
    background-color: #fff;
  }
</style>
