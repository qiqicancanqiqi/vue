<template>
    <div>
        <h4>订单确认</h4>
        <!-- 优惠券单元格 -->
            <van-coupon-cell
            :coupons="coupons"
            :chosen-coupon="chosenCoupon"
            @click="showList = true"
            />
          <van-steps :active="active" active-icon="success" active-color="#38f">
            <van-step>买家下单</van-step>
            <van-step>商家接单</van-step>
            <van-step>买家提货</van-step>
            <van-step>交易完成</van-step>
          </van-steps>
            <van-submit-bar :price="3050" button-text="提交订单" @submit="onSubmit">
            <van-checkbox v-model="checked">全选</van-checkbox>
            <template #tip>
                你的收货地址不支持同城送, <span @click="onClickEditAddress">修改地址</span>
            </template>
            </van-submit-bar>
    </div>
</template>