<template>
    <div>
        <h2>结算</h2>
         <van-goods-action>
                <van-goods-action-icon icon="chat-o" text="客服" color="#ee0a24" />
                <van-goods-action-icon icon="cart-o" text="购物车" />
                <van-goods-action-icon icon="star" text="已收藏" color="#ff5000" />
                <van-goods-action-button type="warning" text="加入购物车" />
                <van-goods-action-button type="danger" text="立即购买" to="/pay"/>
            </van-goods-action>
        <!-- <tab-btn></tab-btn> -->
    </div>
</template>
<script>
import tabBtn from '../components/tabBtn'
export default {
    data() {
        return {
            
        }
    },
}
</script>