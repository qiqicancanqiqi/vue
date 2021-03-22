<template>
  <div class="home" id="home">
      <van-search v-model="searchDate" placeholder="商品搜索，共·1329款好物" input-align='center'/>
      <!-- 轮播 -->
      <van-swipe :autoplay="3000" :width="375" :height='200' >
        <van-swipe-item v-for="(image, index) in images" :key="index">
          <img class="swiperimg" v-lazy="image" />
        </van-swipe-item>
      </van-swipe>
      <!-- 宫格 -->
      <van-grid :column-num="5">
        <van-grid-item v-for="value in 5" icon="photo-o" :key="value" text="文字" />
      </van-grid>
      <!-- 品牌制造商供应面板 -->
      <div class="brandList">
          <van-panel title="品牌制造商供应">
            <van-grid  :column-num="2">
              <van-grid-item  v-for="item in 4" :key="item">
                <van-image fit="cover"  src="https://img01.yzcdn.cn/vant/cat.jpeg">
                <h4 class="title">{{name}}</h4>
                <p class="price">{{price}}</p>
                </van-image>
              </van-grid-item>
            </van-grid>
          </van-panel>
      </div>
        <!-- 新品首发面板 -->
      <div class="newList">
          <van-panel title="新品首发">
            <van-grid  :column-num="2">
              <van-grid-item  v-for="item2 in 4" :key="item2">
                <van-image fit="cover"  src="https://img01.yzcdn.cn/vant/cat.jpeg">
                <h4 class="title " >{{name}}</h4>
                <p class="price">{{price}}</p>
                </van-image>
              </van-grid-item>
            </van-grid>
          </van-panel>
      </div>
      <!-- 人气推荐面板 -->
      <div class="hotlist">
          <van-panel title="人气推荐">
              <van-card v-for="item3 in 3" :key="item3"
                num="20"
                tag="hot"
                price="20.0"
                desc="描述信息"
                title="商品标题"
                thumb="https://img01.yzcdn.cn/vant/ipad.jpeg"
                origin-price="100.00"
              />
          </van-panel>
      </div>
      <div class="tabbar" style="height:50px"></div>
      <tab-btn></tab-btn>
      
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
import api from '../assets/config/api'
import Vue from 'vue';
import less from 'less'
import tabBtn from '../components/tabBtn'
import { Lazyload } from 'vant';
import TabBtn from '../components/tabBtn.vue';
Vue.use(Lazyload);
export default {
  name: 'home',
  data(){
    return{
      searchDate:"",
      name:'漫山红',
      price:'1000000000000',
      tabbleactive:0,
      images: [
        'https://img01.yzcdn.cn/vant/apple-1.jpg',
        'https://img01.yzcdn.cn/vant/apple-2.jpg',
      ],
    }
  },
  components: {
   tabBtn
  },
 mounted(){
    // console.log(api)
  //   axios.get('/api/').then(res=>{
  //     console.log(res.data)
  //   })
  }

}
</script>
<style scoped lang="less">
#home{
  .van-grid-item{
    overflow: hidden;
  }
  .swiperimg{
    width: 375px;
    height: 200px;
  }
  .brandList{
     .van-grid-item__content  {
         padding: 0;
    }
    .van-image{
      border: 1px solid rgb(192, 102, 102);
    }
    .title{
      position: absolute;
      top: 10px;
      left: 10px;
    }
    .price{
      position: absolute;
      top: 40px;
      left: 10px;
      font-size: 14px;
      color: #999 ;
    }
  }
  .newList{
      .title{
      width: 90%;
      overflow: hidden;
      text-overflow: ellipsis;
    }
    .price{
      font-size: 14px;
      color: #999 ;
    }
  }
}
</style>
