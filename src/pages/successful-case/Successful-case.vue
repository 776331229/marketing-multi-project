<template>
  <div>
    <f-header></f-header>
    <!--banner图 start-->
    <div class="banner font-0">
      <router-link :to="{path:'/join'}" tag="a">
        <img src="./../../../static/banner/successfur-banner.png" alt="成功案例">
      </router-link>
    </div>
    <!--banner图 end-->
    <div class="middle font-0">

      <!--萧山机场2 start-->
      <a href="javascript:void (0)" class="testimonial-card airport" style="position: absolute;left: 30px;top:70px">
        <div class="testimonial-fullbleed backImg_airport"></div>
        <div class="row">
          <div class="testimonial-card-text bottom_9 columns medium-5 medium-offset-1">
            <div class="quote">
              <p>萧山机场：付呗为我们定制开发互联网信息服务平台，</p>
              <p>解决“机场三难”问题，汇集机场各方数据，沉淀会员帮助我们</p>
              <p>更好的提供互联网服务，提升旅客出行体验</p>
            </div>
            <div class="row" style="background: #fff">
              <hr class="hr_line">
            </div>
            <div class="row title">
              <div class="testimonial-logo airport_logo">
                <span class="anchor">萧山机场</span>
              </div>
            </div>
          </div>
        </div>
      </a>
      <!--萧山机场2 end-->
      <!--城西银泰城 start-->
      <a href="javascript:void (0)" class="testimonial-card city_west" style="position: absolute;left: 30px;top:523px">
        <div class="testimonial-fullbleed backImg_city_west"></div>
        <div class="row">
          <div class="testimonial-card-text bottom_9 columns">
            <div class="quote">
              <p>杭州城西银泰城：管理会员，精准定位客户，提高会员黏度，</p>
              <p>这些是我们综合体运营的痛点，付呗不但帮我们，整合会员系统，</p>
              <p>对服务进行整合与管理，还建立了数据模型</p>
            </div>
            <div class="row" style="background: #fff">
              <hr class="hr_line">
            </div>
            <div class="row title">
              <div class="testimonial-logo city_west_logo">
                <span class="anchor">杭州城西银泰城</span>
              </div>
            </div>
          </div>
        </div>
      </a>
      <!--城西银泰城 end-->

      <!--左邻右舍 start-->
      <a href="javascript:void (0)" class="testimonial-card left_right" style="position: relative;left: 30px;top:942px">
        <div class="testimonial-fullbleed backImg_left_right"></div>
        <div class="row">
          <div class="testimonial-card-text bottom_9 height small-10 columns">
            <div class="quote">
              <p>左邻右舍：付呗不仅作为一个支付工具，还帮助我们打造了一个</p>
              <p>线上平台对会员进行管理，后期可以对会员进行精准营销</p>
            </div>
            <div class="row" style="background: #fff">
              <hr class="hr_line">
            </div>
            <div class="row title">
              <div class="testimonial-logo left_right_logo">
                <span class="anchor">左邻右舍</span>
              </div>
            </div>
          </div>
        </div>
      </a>
      <!--左邻右舍 end-->

      <!--正新鸡排 start-->
      <a href="javascript:void (0)" class="testimonial-card chicken_chop" style="position: relative;left: 30px;top:941px">
        <div class="testimonial-fullbleed backImg_chicken_chop"></div>
        <div class="row">
          <div class="testimonial-card-text bottom_9 height small-10 columns">
            <div class="quote">
              <p>正新鸡排：接入移动支付是必然趋势，综合考虑那么多家选择付呗</p>
              <p>是因为他们提供的财务管理正好切合我们多门店管理的痛点</p>
            </div>
            <div class="row" style="background: #fff">
              <hr class="hr_line">
            </div>
            <div class="row title">
              <div class="testimonial-logo chicken_chop_logo">
                <span class="anchor">正新鸡排</span>
              </div>
            </div>
          </div>
        </div>
      </a>
      <!--正新鸡排 end-->
      <!--小飞象 start-->
      <a href="javascript:void (0)" class="testimonial-card dumbo" style="position: relative;left: 30px;top:941px">
        <div class="testimonial-fullbleed backImg_dumbo"></div>
        <div class="row">
          <div class="testimonial-card-text bottom_9 small-10">
            <div class="quote">
              <p>小飞象：通过付呗提供的专业支付技术服务，接入多通道付款的</p>
              <p>商户APP与智能POS机与财务系统。客户纷纷反映付款支付流畅</p>
              <p>也大大节省了财务对账的时间，提高了我们的效率</p>
            </div>
            <div class="row" style="background: #fff">
              <hr class="hr_line">
            </div>
            <div class="row title">
              <div class="testimonial-logo dumbo_logo">
                <span class="anchor">小飞象</span>
              </div>
            </div>
          </div>
        </div>
      </a>
      <!--小飞象 end-->
    </div>

    <f-footer></f-footer>
  </div>
</template>

<script>
  import FFooter from 'src/components/f-footer'
  import FHeader from 'src/components/f-header'
  export default{
    components: {
      FHeader,
      FFooter,
    },
    data(){
      return {}
    }
  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/modules/successful-case.less";
</style>
