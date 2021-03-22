<template>
    <div id="category">
        <h4>分类页</h4>
        <van-search v-model="searchDate" placeholder="商品搜索，共·1329款好物" input-align='center'/>
         <!-- 侧边栏 -->
         <van-tree-select 
         :items="items"
         :main-active-index.sync="activeIndex"
         height='calc(100vh - 104px)'
         @click-nav='changeRight'
         >
            <template #content>
                <div class="imgbanner">
                    <img src="https://img01.yzcdn.cn/vant/apple-1.jpg" width="100%" alt="">
                </div>
                <!-- slot=#content定义右侧内容 -->
                <van-grid :column-num="3">
                    <van-grid-item v-for="value in 10" :key="value" icon="photo-o" text="文字" to='/categoryList'>
                        <!-- <img src="" alt="img"> -->
                    </van-grid-item>
                </van-grid>
            </template>
         </van-tree-select>
        <tab-btn></tab-btn>
    </div>
</template>
<script>
import tabBtn from '../components/tabBtn'
export default {
    data() {
        return {
            searchDate:'',
            activeIndex: 0,
             items:[
                        { text: '居家', children: [], dot: true },
                        { text: '餐厨', children: [], badge: 5 },
                        { text: '饮食', children: [] },
                        { text: '配件', children: []},
                        { text: '服装', children: [] },
                        { text: '江苏', children: [] },
                        { text: '浙江', children: [] },
                    ],
            
            
        }
    },
     methods:{
        changeRight(index){
            console.log(index)
        }
    },
    components:{
        tabBtn
    },
   
}
</script>
<style lang="less">
#category{
    .imgbanner{
        width: 100%;
        
        box-sizing:boeder-box;
        padding: 10px;
        img{
            height: 120px;
            width: 100%;
        }
    }
}
</style>