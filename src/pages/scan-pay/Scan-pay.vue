<template>
  <div >
    <f-header></f-header>
    <!--轮播图 start-->
    <div class="banner">
      <router-link :to="{path:'/join'}" tag="a"><img src="../../../static/banner/Sbanner.png" alt=""></router-link>
    </div>
    <!--轮播图 end-->

    <!--二维码支付-->
    <f-module class="code-pay">
      <div class="type-page pay-box">
        <div class="payTitle text-center">
          <p class="font-xi size-34 font-color-21">二维码支付<i class="line"></i><span class="font-color-blue">多码合一</span></p>
          <p class="font-siyuan font-18 font-color-666" style="margin: 25px 0 0">集合多种支付模块，最便捷的优惠买单方式</p>
        </div>
        <div class="pay-process">
          <div class="inline-block">
            <img src="../../../static/scanPay/phone1.png" alt="">
            <div class="line-height-20 margin-top13">
              <p>“扫一扫”</p>
              <p>生活圈商户二维码</p>
            </div>
          </div>
          <div class="deal-pro inline-block">
            <img src="../../../static/scanPay/phone2.png" alt="">
            <p class="margin-top25">输入消费金额</p>
          </div>
          <div class="deal-pro inline-block">
            <img src="../../../static/scanPay/phone3.png" alt="">
            <p class="margin-top25">输入密码，确认支付</p>
          </div>
          <div class="deal-pro inline-block">
            <img src="../../../static/scanPay/phone4.png" alt="">
            <p class="margin-top25" >支付成功</p>
          </div>
        </div>
      </div>
    </f-module>

    <!--掌上生意 start-->
    <div class="handle">
      <!--<div class="type-page">-->
      <div class="type-page ">
        <div class="handle-title text-center padding-top-70">
          <p class="font-xi size-34 font-color-21">APP<i class="line"></i><span class="font-color-blue">随时随地掌上生意</span></p>
        </div>
        <!--</div>-->

        <div class="handle-middle margin-top-40">
          <!--<div class="type-page">-->
          <!--扫码支付 + 门店管理 tab-->
          <div class="dis-inline-block handle-left sweep float-left">
            <!--扫码支付 tab-->
            <f-handle class="margin-bottom70" :class="{'small-trangle-l':type==1}" style="text-align: right" @changeStatus="change(1)">
              <div class="inline-block font-xi">
                <h3>扫码支付</h3>
                <h5>告别假币，随时随地可收钱</h5>
              </div>
              <div class="dis-inline-block marginBesides-25">
                <img src="../../assets/images/scanPay/scanPay.png" alt="">
              </div>
            </f-handle>
            <!--门店管理 tab-->
            <f-handle :class="{'small-trangle-l':type==2}" style="text-align: right" @changeStatus="change(2)">
              <div class="inline-block font-xi">
                <h3>门店管理</h3>
                <h5>门店经营详情实时查看</h5>
                <h5>员工数据汇总，绩效考核一键完成</h5>
              </div>
              <div class="right inline-block marginBesides-15-24">
                <img src="../../assets/images/scanPay/store.png" alt="">
              </div>
            </f-handle>
          </div>

          <!--手机样式 图片 start-->
          <div class="handle-pic dis-inline-block">
            <img :src="appPic" alt="手机图片">
          </div>
          <!--手机样式 图片 end-->

          <!--订单管理 tab-->
          <div class="dis-inline-block handle-right float-right">
            <f-handle class="margin-bottom70" :class="{'small-trangle-r':type==3}" @changeStatus="change(3)">
              <div class="right inline-block marginBesides-29-20">
                <img src="../../assets/images/scanPay/order.png" alt="">
              </div>
              <div class="inline-block font-xi">
                <h3>订单管理</h3>
                <h5>实时对账，了解所有交易数据</h5>
              </div>
            </f-handle>

            <!--会员管理 tab-->
            <f-handle class="" :class="{'small-trangle-r':type==4}" @changeStatus="change(4)">
              <div class="right inline-block marginBesides-29-17">
                <img src="../../assets/images/scanPay/member.png" alt="">
              </div>
              <div class="inline-block font-xi">
                <h3>会员管理</h3>
                <h5>有效管理会员，发布会员活动</h5>
                <h5>会员数据分析</h5>
              </div>
            </f-handle>

          </div>
        </div>
      </div>
      <!--</div>-->
    </div>
    <!--掌上生意 end-->


    <!--PC 收银台页面 start-->
    <f-module class="pc-big-box padding-top-95 margin-bottom-85 margin-left-50 ">
      <div class="pc-title text-center">
        <p class="font-34 font-xi color-gary">pc收银台<i class="line-one"></i><span class="font-34 font-xi font-color-blue margin-left-55">兼容主流客显收银台</span></p>
        <p class="font-18 font-siyuan color-cameo margin-top-20">无需打通系统、无需切换界面、无需输入金额、简简单单的完成收款</p>
      </div>
    </f-module>
    <!--PC 收银台页面 end-->

    <!--支付展示页面 标题 start-->
    <f-module class="pay-title-box">
      <div class="pay-title text-center">
        <i class="line-one"></i><p class="pay-character font-xi font-24 font-color-21 ">支付、卡券核销、电子会员，<span class="font-color-blue">一键搞定</span></p><i class="line-two"></i>
      </div>
    </f-module>
    <!--支付展示页面 标题end-->

    <!--支付显示页面 start-->
    <f-module class="pay-view">
      <div class="padding-top-66">
        <router-view></router-view>
      </div>
    </f-module>
    <!--支付显示页面 end-->

    <!--支付tab点击页面 start-->
    <f-module class="pay-tab font-0">
      <ul class="pay-3-box">
        <i class="tab-logo"></i>
        <li class="font-xi font-20 color-cameo"><router-link to="payment" tag="a" class="pay-link"> 支付流程</router-link></li>
        <li class="font-xi font-20 color-cameo"><router-link to="coupon" tag="a">卡券核销流程</router-link></li>
        <li class="font-xi font-20 color-cameo"><router-link to="membership" tag="a" class="pay-link">电子会员</router-link></li>
      </ul>
    </f-module>

    <!--POS 支付页面 start-->
    <f-module class="pos-big-box margin-top-90">
      <!--pos 支付页面标题 start-->
      <div class="pos-title text-center">
        <p class="font-34 font-xi color-gary pos-words">POS<i class="line-one"></i><span class="font-34 font-color-blue font-xi margin-left-55">融合商用场景进行优化，实现最佳优化解决方案</span></p>
      </div>
      <!--pos 支付页面标题 end-->

      <!--pos 支付页面描述 start-->
      <div class="pos-notes margin-top-90 dis-inline-block">
        <div class="pos-description margin-left-93 dis-inline-block">
          <p class="font-siyuan font-30 color-gary margin-bottom-33 font-weight-1">5.5英寸IPSqHD,全高清阳光屏</p>
          <ul class="line-height-30">
            <li class="font-siyuan font-18 color-cameo">分辨率960*540：清晰度提升1.5倍，兼容性最强</li>
            <li class="font-siyuan font-18 color-cameo">采用IPS技术：可视角度达178°，让用户不正对屏幕也能看清</li>
            <li class="font-siyuan font-18 color-cameo">5.5英寸屏幕：市场移动设备主流尺寸，体验好，适合单手把持</li>
            <li class="font-siyuan font-18 color-cameo">电容式多点触屏：看图片可调节图片大小</li>
          </ul>
          <div class="margin-top-64">
            <img src="../../../static/scanPay/5.5brick.png" alt="5.5 tu" title="5.5">
          </div>
        </div>

        <!--pos 支付logo start-->
        <div class="pos-logo dis-inline-block">
          <img src="../../../static/scanPay/POS.png" alt="pos logo tu" title="pos logo">
        </div>
        <!--pos 支付logo end-->
      </div>
    </f-module>
    <!--POS 支付页面 end-->

    <!--POS 支付展示页面 start-->
    <f-module class="pos-show">
      <!--支付展示大盒子-->
      <div class="show-big-box padding-top-50">
        <!--四个信息大盒子-->
        <div class="box-four font-0">
          <!--1、团购 start-->
          <div class="show-box-one bg-white dis-inline-block text-center margin-right-176 margin-bottom-50">
            <div class="show-logo dis-inline-block margin-top-25 margin-bottom-15">
              <img src="../../../static/scanPay/groupon.png" alt="groupon tu logo" title="groupon">
            </div>
            <div class="show-notes ">
              <p class="font-xi font-20 color-gary margin-bottom-15">团购、卡券、核销 </p>
              <p class="font-xi font-16 color-cameo">0.7秒快速扫二维码进行核销</p>
            </div>
          </div>
          <!--2、会员卡 start-->
          <div class="show-box-one bg-white dis-inline-block text-center margin-bottom-50">
            <div class="show-logo dis-inline-block margin-top-25 margin-bottom-15">
              <img src="../../../static/scanPay/recharge.png" alt="recharge tu logo" title="recharge">
            </div>
            <div class="show-notes">
              <p class="font-xi font-20 color-gary margin-bottom-10">会员卡充值消费 </p>
              <p class="font-xi font-16 color-cameo">顾客在线申请会员卡，享受会员权益,</p>
              <p class="font-xi font-16 color-cameo">通过扫描会员卡条码即可完成充值及消费</p>
            </div>
          </div>
          <!--3、移动支付-->
          <div class="show-box-one bg-white dis-inline-block text-center margin-right-176">
            <div class="show-logo dis-inline-block margin-top-25 margin-bottom-15">
              <img src="../../../static/scanPay/payment.png" alt="payment tu logo" title="payment">
            </div>
            <div class="show-notes">
              <p class="font-xi font-20 color-gary margin-bottom-15">移动支付 </p>
              <p class="font-xi font-16 color-cameo">支持付呗商户版、微信、支付宝、二维码</p>
            </div>
          </div>
          <!--排队预约-->
          <div class="show-box-one bg-white dis-inline-block text-center ">
            <div class="show-logo dis-inline-block margin-top-25 margin-bottom-15">
              <img src="../../../static/scanPay/reservation.png" alt="reservation tu logo" title="reservation">
            </div>
            <div class="show-notes">
              <p class="font-xi font-20 color-gary margin-bottom-15">排队预约 </p>
              <p class="font-xi font-16 color-cameo">连续打印5000笔订单，高峰期使用更方便</p>
            </div>
          </div>
          <!--加号-->
          <div class="sign-box"></div>
        </div>
      </div>
    </f-module>
    <!--POS 支付展示页面 end-->

    <!--API 支付 start-->
    <f-module class="api-big-box dis-inline-block margin-bottom-80">
      <div class="section">
        <div class="api-title dis-inline-block text-center margin-top-100">
          <p class="api-tag font-xi font-34 font-color-21 ">一个API
            <i class="line-one"></i>
            <span class="margin-left-55 font-xi font-34 font-color-blue">在任何平台和场景接入支付</span>
          </p>
        </div>
        <div class="api-words dis-inline-block text-left">
          <p class="font-siyuan font-24 color-gary font-weight-1">我们将</p>
          <p class="font-words-two font-xi-2 font-24 margin-top-18">支付宝、微信的刷卡、扫码支付功能</p>
          <ul class="font-3-box">
            <li class="margin-top-28 font-siyuan font-20 color-cameo">通过<i class="api-port"></i><span class="margin-left-80">的方式开放给合作商户</span>
            </li>
            <li class="margin-top-28 float-left font-siyuan font-20 color-cameo">商户通过接入生活圈开放平台</li>
            <li class="margin-top-28 float-left font-siyuan font-20 color-cameo">来实现使用自己的商户系统进行收款</li>
          </ul>
        </div>
      </div>
    </f-module>
    <!--API 支付 end-->
    <f-footer></f-footer>
  </div>
</template>
<script>
  import fHandle from '../../components/f-handle/index.vue'
  import FFooter from 'src/components/f-footer'
  import FHeader from 'src/components/f-header'
  import FModule from 'src/components/f-module/index.vue'
  import appPic from '../../../static/app-handle/scan4.png'
  export default {
    components: {
      fHandle,
      FModule,
      FHeader,
      FFooter,
    },
    data() {
      return {
        type:1,
        appPic: appPic
      }
    },
    watch:{
      type(){
        switch (this.type){
          case 1:this.appPic = '../../../static/app-handle/scan4.png';break;
          case 2:this.appPic = '../../../static/app-handle/Store3.png';break;
          case 3:this.appPic = '../../../static/app-handle/indent1.png';break;
          case 4:this.appPic = '../../../static/app-handle/member2.png';break;
          default:break;
        }
      }
    },
    methods:{
      change(no){
        this.type=no;
//        console.log(this.type)
      }
    }
  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/modules/scan-pay.less";
</style>
