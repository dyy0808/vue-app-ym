<template>
   <div class="footer">
        <nav class="mui-bar mui-bar-tab">
            <router-link to="/" class="mui-tab-item mui-active" href="#tabbar">
            <router-link to="/index">
                <span class="mui-icon mui-icon-home"></span>
                <span class="mui-tab-label">首页</span>
            </router-link>
            </router-link>
            <a class="mui-tab-item" href="#tabbar-with-chat">
                <router-link to="/list">
                    <span class="mui-icon mui-icon-email"></span>
                     <span class="mui-tab-label">商品</span>
                </router-link>
            </a>
            <a class="mui-tab-item" href="#tabbar-with-contact">
                <router-link to="/cart">
                    <span class="mui-icon mui-icon-extra mui-icon-extra-cart"><span class="mui-badge">0</span></span>
                    <span class="mui-tab-label">购物车</span>
                </router-link>
            </a>
            <a class="mui-tab-item" href="#tabbar-with-map">
                <span v-if="userName">
                    <router-link to="/vip">
                        <span class="mui-icon mui-icon-search"></span>
                        <span class="mui-tab-label">会员中心</span>
                    </router-link>
                </span>
                <span v-else>
                    <router-link to="/login">
                        <span class="mui-icon mui-icon-search"></span>
                        <span class="mui-tab-label">会员中心</span>
                    </router-link>
                </span>
            </a>
        </nav>
   </div>
</template>
<script>
export default {   
    data() {  
    return {
         userName:sessionStorage.getItem("userName")
        }
    },
    created(){
        console.log(this.userName)
    }
}
</script>
<style>

</style>

