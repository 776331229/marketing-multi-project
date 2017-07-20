<template>
  <div class="pay-super-box dis-inline-block overflow-hide" >
    <div class="payment-big-box text-center dis-inline-block" v-if="type==1">
      <div class="payment-box dis-inline-block">
        <img src="../../../static/scanPay/pay.png" alt="pay logo" title="pay tu">
      </div>
      <div class="payment-collection dis-inline-block margin-top-24">
        <p class="dis-inline-block pay-one font-siyuan">1、用户打开支付宝钱包</p>
        <p class="dis-inline-block pay-two font-siyuan">2、出示付款码</p>
        <p class="dis-inline-block pay-three font-siyuan">3、收银员扫码</p>
        <p class="dis-inline-block pay-four font-siyuan">4、付款成功</p>
      </div>
    </div>

    <div class="voucher-big-box text-center dis-inline-block" v-if="type==2">
      <div class="voucher-box">
        <img src="../../../static/scanPay/voucher.png" alt="pay logo" title="pay tu">
      </div>
      <div class="voucher-collection dis-inline-block margin-top-20">
        <p class="dis-inline-block pay-one font-16 font-siyuan">1、选择"卡券核销功能"</p>
        <p class="dis-inline-block pay-two font-16 font-siyuan">2、打开支付宝钱包，点开需要<br/>核销的卡券/优惠券，扫描条形码</p>
        <p class="dis-inline-block pay-three font-16 font-siyuan">3、完成卡券核销</p>
        <p class="dis-inline-block pay-four font-16 font-siyuan">4、卡券核销完成</p>
      </div>
    </div>

    <div class="membership-big-box text-center dis-inline-block" v-if="type==3">
      <div class="membership-box">
        <img src="../../../static/scanPay/membership.png" alt="pay logo" title="pay tu">
      </div>
      <div class="membership-collection dis-inline-block margin-top-20">
        <p class="dis-inline-block pay-one font-16 font-siyuan color-cameo">1、付呗pc版，会员充值，输入金额</p>
        <p class="dis-inline-block pay-two font-16 font-siyuan color-cameo">2、打开支付宝钱包，选择商家会员卡<br/>点开会员卡条形码</p>
        <p class="dis-inline-block pay-three font-16 font-siyuan color-cameo">3、充值成功，消费直接使用</p>
      </div>
    </div>


  </div>
</template>
<script>
  export default {
    props:{
      type:{
        type:Number,
        default:1
      }
    },
    data() {
      return {

      }
    },
    mounted(){
      console.log(this.type);
    }
  }
</script>
<style lang="less" scoped>
  @import 'index.less';
</style>
