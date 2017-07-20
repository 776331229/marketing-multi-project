<template>
  <div class="supper-big-box overflow-hide dis-inline-block">
    <!--二维码收款 start-->
    <div class="code-box dis-inline-block" v-if="type==1">
      <div class="pay-box dis-inline-block float-left margin-left-20">
        <img src="../../../static/home/payment/qrcode/qrcode.png" alt="er wei ma logo" title="二维码logo">
      </div>
      <div class="dis-inline-block pay-words text-left margin-left-40">
        <p class="font-xi font-style-28 font-color">纷杂世界，一个就够了</p>
        <p class="font-xi font-style-30  margin-top-20 margin-bottom-20">多码合一，集合多种支付模块</p>
        <p class="font-xi confirm-logo   float-left">支持：</p><img src="../../../static/home/payment/qrcode/logo.png" alt="">
      </div>
    </div>
    <!--二维码收款 end-->

    <!--app收款 start-->
    <div class="app-box dis-inline-block" v-if="type==2">
      <div  class="">
        <p class="font-style font-xi">随时随地掌上生意</p>
      </div>
      <div class="app-style">
        <img src="../../../static/home/payment/app/app.png" alt="app logo" title="app logo">
      </div>
      <div class="app-collection dis-inline-block">
        <p class="dis-inline-block pay-one font-siyuan">收银员打开付呗APP</p>
        <p class="dis-inline-block pay-two font-siyuan">点击收款进入、输入金额</p>
        <p class="dis-inline-block pay-three font-siyuan">扫描用户二维码</p>
        <p class="dis-inline-block pay-four font-siyuan">付款成功</p>
      </div>
    </div>
    <!--app收款 end-->

    <!--扫码枪 start-->
    <div class="scan-box dis-inline-block" v-if="type==3">
      <div >
        <p class="font-style font-xi">无需打通系统、无需切换界面、无需输入金额、扫码枪轻松收款</p>
      </div>
      <div class="scan-style">
        <img src="../../../static/home/payment/scan/scan.png" alt="">
      </div>
      <div class="scan-collection dis-inline-block">
        <p class="dis-inline-block scan-one font-siyuan">用户打开支付宝钱包</p>
        <p class="dis-inline-block scan-two font-siyuan">出示付款码</p>
        <p class="dis-inline-block scan-three font-siyuan">收银员扫码</p>
        <p class="dis-inline-block scan-four font-siyuan">付款成功</p>
      </div>
    </div>
    <!--扫码枪 end-->

    <!--pos收款 start-->
    <div class="pos-big-box dis-inline-block" v-if="type==4">
      <!--pos 支付标题 start-->
      <p class="font-xi pos-title">融合商用场景进行优化，实现最佳优化解决方案</p>
      <!--pos 图片+描述-->
      <div class="pos-box dis-inline-block float-left margin-top-50">
        <div class="dis-inline-block margin-right-48 pos-logo float-left">
          <img src="../../../static/home/payment/pos/pos.png" alt="pos logo" title="pos logo">
        </div>
        <div class="dis-inline-block pos-notes text-left">
          <p class="title-one font-siyuan font-20 font-weight-1">付呗v5POS机</p>
          <p class="title-two float-left font-siyuan font-22 margin-top-20 font-weight-1">5.5英寸IPSqHD,全高清阳光屏</p>
          <ul class="pos-title-four line-height-36">
            <li class="float-left font-siyuan font-16 margin-left-20"><i class="circle"></i>分辨率960*540：清晰度提升1.5倍，兼容性最强</li>
            <li class="float-left font-siyuan font-16 margin-left-20"><i class="circle"></i>采用IPS技术：可视角度达178°，让用户不正对屏幕也能看清</li>
            <li class="float-left font-siyuan font-16 margin-left-20"><i class="circle"></i>5.5英寸屏幕：市场移动设备主流尺寸，体验好，适合单手把持</li>
            <li class="float-left font-siyuan font-16 margin-left-20"><i class="circle"></i>电容式多点触屏：看图片可调节图片大小</li>
          </ul>
        </div>
      </div>
    </div>
    <!--pos收款 end-->

    <!--api收款 start-->
    <div class="api-box dis-inline-block" v-if="type==5">
      <!--api logo-->
      <div class="api-logo dis-inline-block float-left margin-right-48 margin-left-30">
        <img src="../../../static/home/payment/api/api.png" alt="api logo" title="api logo">
      </div>
      <!--api 描述-->
      <div class="api-words dis-inline-block text-left margin-right-48">
        <p class="font-siyuan font-24 color-gary font-weight-1">我们将</p>
        <p class="font-words-two font-xi-2 font-24 margin-top-18">支付宝、微信的刷卡、扫码支付功能</p>
        <ul class="font-3-box">
          <li class="margin-top-28 font-siyuan font-20 color-cameo">通过<i class="api-port"></i><span class="margin-left-80">的方式开放给合作商户</span></li>
          <li class="margin-top-28 float-left font-siyuan font-20 color-cameo">商户通过接入生活圈开放平台</li>
          <li class="margin-top-15 float-left font-siyuan font-20 color-cameo">来实现使用自己的商户系统进行收款</li>
        </ul>
      </div>
    </div>
    <!--api收款 end-->


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
  @import "./index.less";
</style>
