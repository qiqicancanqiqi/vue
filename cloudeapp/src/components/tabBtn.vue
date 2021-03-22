<template>
      <van-tabbar v-model="tabActive">
        <van-tabbar-item icon="home-o" to='/'>首页</van-tabbar-item>
        <van-tabbar-item icon="cluster-o" to='/category'>分类</van-tabbar-item>
        <van-tabbar-item icon="friends-o" to="/categoryList">专题分类</van-tabbar-item>
        <van-tabbar-item icon="shopping-cart-o" to='/buy' >购物车</van-tabbar-item>
        <van-tabbar-item link-to="/cataory" icon="user-o" to="/me" >我的</van-tabbar-item>
      </van-tabbar>
</template>
<script>
export default {
    data(){
        return{
            // v-model 默认绑定选中标签的索引值，通过修改 v-model 即可切换选中的标签。
            tabActive:0
        }
    },
    mounted() {
           switch(this.$router.path){
                 case "/category": this.tabActive=1 
                        break;
                case '/':this.tabActive=0  
                        break;
                case "/categoryList": this.tabActive=2
                        break;
                case "/buy": this.tabActive=3 
                break;
                case "/me": this.tabActive=4
                break;
                default:this.tabActive=0
            }
    },
    
}
</script>