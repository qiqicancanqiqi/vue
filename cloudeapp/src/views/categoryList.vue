<template>
    <div id="categoryList">
        <h4>产品分类列表</h4>
        <!-- 头部导航 -->
            <van-tabs v-model="tabactive">
                <van-tab title="标签 1">内容 1</van-tab>
                <van-tab title="标签 2">内容 2</van-tab>
                <van-tab title="标签 3">内容 3</van-tab>
                <van-tab title="标签 4">内容 4</van-tab>          
            </van-tabs>
            <!-- 宫格 -->
            <van-grid :border="false" :column-num="2">
                <van-grid-item v-for="item2 in 6" :key="item2" to='/buy'>
                    <van-card
                    num="2"
                    tag="标签"
                    price="2.00"
                    desc="描述信息"
                    title="商品标题"
                    thumb="https://img01.yzcdn.cn/vant/ipad.jpeg"
                    origin-price="10.00"
                    />
                 </van-grid-item>
            </van-grid>
           
        <tab-btn></tab-btn>
    </div>
</template>
<script>
import tabBtn from '../components/tabBtn'

export default {
  components: { tabBtn },
    data() {
        
        return {
            tabactive:0
        }
    },
}
</script>