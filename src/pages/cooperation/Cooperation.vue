<template>
  <div>
    <f-header></f-header>
    <!--轮播图 start-->
    <swiper :options="swiperOption" ref="mySwiper" style="width: 100%;" class="swiper-big-box margin-bottom75">
      <!-- 幻灯内容 -->
      <swiper-slide v-for="n in 4" :key="n" class="swiper-box">
        <div class="swiper-pic">
          <router-link :to="{path:'/join'}" tag="a"><img :src="'static/banner/banner'+n+'.png'" alt="" style="width: 100%;"></router-link>
        </div>
        <!--左右按钮-->
      </swiper-slide>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>
    <!--轮播图 end-->
    <!--支付宝开发商top5 start-->
    <f-module class="font-0">
      <!--top5大盒子-->
      <div class="top5 type-page">
        <div class="top-title text-center font-0 font-xi">
          <p class="font-34 color-2121">移动支付首批授权服务商+全国支付宝开发商<span class="font-lan">TOP5</span></p>
          <p class="font-18 font-color-666 margin-top-15">我们做的不是pos机，我们做的是移动支付和商户开发运营全系列解决方案</p>
        </div>
        <div class="top-detail font-0 margin-top-68">
          <div class="service service-pic"></div>
          <div class="service benefit color-cameo font-siyuan">
            <div class="benefit-detail margin-top-45 margin-bottom-60">
              <!--<div class="money icon1 margin-right-30"></div>-->
              <IonicBox :width="47" :height="47" :src="require('./../../assets/images/cooperation/get-money.png')"></IonicBox>
              <div class="inline-block text-center">
                <p class="font-20 margin-bottom-16">收入不至于分润，更是开发与运营收益</p>
                <p class="font-20">让商户更懂营销，收入更快更多元</p>
              </div>
            </div>
            <div class="benefit-detail">
              <!--<div class="money icon2 margin-right-29"></div>-->
              <IonicBox :width="50" :height="49" :src="require('./../../assets/images/cooperation/service.png')"></IonicBox>
              <div class="inline-block text-center">
                <p class="font-20 margin-bottom-16">服务不至于产品，更是渠道与运营技巧</p>
                <p class="font-20">让代理更懂市场，收入更多更持久</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </f-module>
    <!--支付宝开发商top5 end-->
    <!--资质特权 start-->
    <f-module class="Qualification-privilege module-bg-blue">
      <div class="Qualification type-page text-center padding-top-90">
        <div class="font-xi">
          <p class="font-34 color-2121"><i class="line"></i><span class="margin-left-24 margin-right-24">资质特权</span><i
            class="line"></i></p>
          <p class="font-20 color-cameo margin-top-19"><span class="font-lan">官方实力认可</span>，为代理商提供品牌支持、资质证明、优秀案例</p>
        </div>
        <div class="privileges margin-top-65 margin-bottom75 font-xi color-cameo">
          <div class="privilege inline-block margin-right-63">
            <img src="../../../static/cooperation/alipay-isv.png" alt="">
            <p class="margin-top-19">支付宝授权ISV</p>
          </div>
          <div class="privilege inline-block margin-right-62">
            <img src="../../../static/cooperation/ali.png" alt="">
            <p class="margin-top-19">支付宝未来商圈合作伙伴</p>
          </div>
          <div class="privilege inline-block margin-right-63">
            <img src="../../../static/cooperation/alipay-activity.png" alt="">
            <p class="margin-top-19">支付宝官方活动技术支持</p>
          </div>
          <div class="privilege inline-block">
            <img src="../../../static/cooperation/alipay-cooper.png" alt="">
            <p class="margin-top-19">业内唯一受邀参加阿里云大会</p>
          </div>
        </div>
      </div>
    </f-module>
    <!--资质特权 end-->
    <!--明显优势 start-->
    <f-module>
      <div class="type-page padding-top-80 padding-bottom-70">
        <!--顶部文字部分-->
        <div class="margin-bottom-60">
          <h3 class="text-center font-xi font-34 color-2121 margin-bottom-30">我们有什么明显的<span class="font-lan">优势</span>呢?
          </h3>
          <p class="font-14 font-siyuan color-cameo line-height-24 margin-bottom-14">
            付呗是中国领先的移动支付一站式解决方案服务提供商。核心成员来自阿里巴巴，具备强大的技术开发、运营、营销团队。付呗是支付宝首批ISV（系统软件开发商），目前是唯一一家拥有景区代理权限的ISV，并且是支付宝口碑推荐服务商。目前达成移动支付合作伙伴包括 14个商城、6个商业街、5个机场、4个广场、以及十万多家中小型商户。能够提供给代理商完善的产品培训，市场支持，品牌扶持，渠道输出，官方特权，技术开发等服务</p>
          <p class="font-14 font-siyuan color-cameo line-height-24">
            付呗数年来的技术积累使产品最为齐全，全方位覆盖各种需求的商户，创新性的推出了多种产品，有助于更好的抢占市场。付呗理念积累的培训经验有助于让代理商更好更快的开拓市场。</p>
        </div>
        <!--手风琴样式图片部分-->
        <div class="box case-logo-list-box">
          <ul class="clearfix">
            <li>
              <i class="logo-icon icon-1"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-2"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-3"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-4"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-5"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-6"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-7"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-8"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-9"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-10"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-11"></i>
            </li>
            <li class="">
              <i class="logo-icon icon-12"></i>
            </li>
          </ul>
        </div>
        <!--更多品牌案例-->
        <div class="text-center">
          <p class="font-24 font-xi color-999 margin-bottom-40">更多品牌案例，更多项目优势......</p>
          <div class="font-siyuan font-16 color-cameo hot-line">抢占巨大的移动支付市场<i class="inline-block"
                                                                              style="width: 15px;"></i>加盟热线 : <span
            class="font-lan">0571-88533296</span></div>
        </div>
      </div>
    </f-module>
    <!--明显优势 end-->
    <!--加盟优势 start-->
    <f-module class="join-advantage">
      <div class="Qualification type-page text-center padding-top-90 padding-bottom-90">
        <div class="font-xi">
          <p class="font-34 color-2121"><i class="line"></i>
            <span class="margin-left-24 margin-right-24">加盟优势</span>
            <i class="line"></i></p>
          <p class="font-20 color-cameo margin-top-19">及时提供最低门槛<span class="font-lan">官方活动政策</span>，帮助代理商服务商户 ，更多佣金分润
          </p>
        </div>
        <!--立减3元-->
        <div class="privileges margin-top-65">
          <div class="privilege inline-block discount">
            <img src="../../../static/cooperation/1.png" alt="" class="padding-top-6 padding-bottom-10">
            <p class="font-xi font-14 color-gary font-weight-1">每周三、四，满20元立减3元</p>
          </div>
          <div class="privilege inline-block margin-left-70 discount">
            <img src="../../../static/cooperation/2.png" alt="" class="padding-top-6 padding-bottom-10">
            <p class="font-xi font-14 color-gary font-weight-1 ">支付宝奖励金海报</p>
          </div>
          <div class="privilege inline-block margin-left-70 discount">
            <img src="../../../static/cooperation/3.png" alt="" class="padding-top-6 padding-bottom-10">
            <p class="font-xi font-14 color-gary font-weight-1">每周二、四，满10元立减3元</p>
          </div>
          <div class="privilege inline-block margin-left-70 discount">
            <img src="../../../static/cooperation/4.png" alt="" class="padding-top-6 padding-bottom-10">
            <p class="font-xi font-14 color-gary font-weight-1">付呗鸡年新春活动</p>
          </div>
        </div>
      </div>
    </f-module>
    <!--加盟优势 end-->
    <!--营销补贴活动 start-->
    <f-module class="Subsidy-activities">
      <div class="type-page padding-top-118 padding-bottom-56">
        <div class="subsidy inline-block font-0">
          <div class="subsidy-title font-30 font-xi-2 color-gary">
            <p class="margin-bottom-18">除了官方活动，</p>
            <p class="margin-bottom-28">付呗推出自己营销补贴活动</p>
          </div>
          <p class="font-41 font-xi-2 color-orange text-right"><i class="orange-line"></i>飓风激励</p>
          <div class="mark-money"></div>
        </div>
        <div class="activities inline-block font-0 margin-left-200">
          <img src="../../../static/cooperation/activity.png" alt="">
        </div>
      </div>
    </f-module>
    <!--营销补贴活动 end-->
    <!--服务支持 start-->
    <f-module class="service-support">
      <div class="section type-page text-center">
        <div class="font-xi">
          <p class="font-34 color-2121"><i class="line"></i><span class="margin-left-24 margin-right-24">服务支持</span><i
            class="line"></i></p>
          <p class="font-20 color-cameo margin-top-10">渠道、产品、运营、技术<span class="font-lan">全方位扶持</span>代理商，更高品质的产品与服务</p>
        </div>
        <div class="support-reason">
          <div class="reason-content">
            <!--盒子左边部分-->
            <div class="inline-block margin-right-112" style="width: 470px">
              <div class="reason-box text-left margin-bottom-47 font-0">
                <div class="reason-head font-20 font-xi color-cameo margin-bottom-19">
                  <img class="margin-right-20 ver-align-m" src="../../assets/images/cooperation/icon1.png" alt="">
                  <span class="ver-align-m "><i class="ver-title"></i>不懂技术？</span>
                </div>
                <div class="readon-body font-16 font-siyuan color-cameo line-height-30">
                  <p>1、总部提供专业研发团队，优先处理合作伙伴的定制与开发商家</p>
                  <p>2、总部提供7*12小时技术服务支持，在线工单随时响应</p>
                  <p>3、付呗在线培训，每周开课，帮助伙伴从零到一</p>
                </div>
              </div>
              <div class="reason-box text-left font-0">
                <div class="reason-head font-20 font-xi color-cameo margin-bottom-19">
                  <img class="margin-right-20 ver-align-m" src="../../assets/images/cooperation/icon2.png" alt="">
                  <span class="ver-align-m"><i class="ver-title"></i>不会运营？</span>
                </div>
                <div class="readon-body font-16 font-siyuan color-cameo line-height-30">
                  <p>1、总部提供付呗产品活动策划，营销推广，代运营等建议</p>
                  <p>2、付呗提供付呗总裁班，阿里铁军出品《产品、市场、团队管理全方位总裁班培训》</p>
                </div>
              </div>
            </div>
            <!--盒子右边部分-->
            <div class="inline-block margin-left-60">
              <div class="reason-box text-left margin-bottom78 font-0">
                <div class="reason-head font-20 font-xi color-cameo margin-bottom-19">
                  <img class="margin-right-20 ver-align-m" src="../../assets/images/cooperation/icon3.png" alt="">
                  <span class="ver-align-m"><i class="ver-title"></i>不懂产品？</span>
                </div>
                <div class="readon-body font-16 font-siyuan color-cameo line-height-30">
                  <p>1、总部提供国内最顶级的移动支付，硬件成本价供给</p>
                  <p> 2、免费产品迭代升级，支持多种方式完成线下支付</p>
                </div>
              </div>
              <div class="reason-box text-left font-0">
                <div class="reason-head font-20 font-xi color-cameo margin-bottom-19">
                  <img class="margin-right-20 ver-align-m" src="../../assets/images/cooperation/icon4.png" alt="">
                  <span class="ver-align-m"><i class="ver-title"></i>没有渠道？</span>
                </div>
                <div class="readon-body font-16 font-siyuan color-cameo line-height-30">
                  <p>1、总部全国营销推广获取商户资源，无条件分配当地合作伙伴</p>
                  <p>2、丰富的一线市场地推经验，驻点帮助合作伙伴提升业务能力</p>
                  <p>3、蚂蚁金服金牌讲师会议支持，KA客户谈判支持</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </f-module>
    <!--服务支持 end-->
    <!--加盟流程 start-->
    <f-module class="join-process bg-light-blue">
      <div class="section type-page text-center">
        <!--模块标题部分-->
        <div class="font-xi">
          <p class="font-34 color-2121"><i class="line"></i><span class="margin-left-24 margin-right-24">加盟流程</span><i
            class="line"></i></p>
          <p class="font-20 color-cameo margin-top-10">专属经理对接，全程跟踪服务，长久合作共赢</p>
        </div>
        <!--模块主体部分-->
        <div class="processes">
          <div class="process inline-block margin-right-100 color-cameo font-siyuan">
            <img src="../../../static/cooperation/process/process-1.png" alt="">
            <p class="font-20 margin-top-25 margin-bottom-18">合作签约</p>
            <span class="font-14">对接专属渠道经理</span>
          </div>
          <div class="process inline-block margin-right-100 color-cameo font-siyuan">
            <img src="../../../static/cooperation/process/process-2.png" alt="">
            <p class="font-20 margin-top-25 margin-bottom-18">合作伙伴归档</p>
            <span class="font-14">分配专属服务对接人</span>
          </div>
          <div class="process inline-block margin-right-100 color-cameo font-siyuan">
            <img src="../../../static/cooperation/process/process-3.png" alt="">
            <p class="font-20 margin-top-25 margin-bottom-18">运营团队对接</p>
            <span class="font-14 margin-bottom-7">日常售后专属经理</span>
            <p class="font-14">区域业务专属市场顾问</p>
          </div>
          <div class="process inline-block margin-right-100 color-cameo font-siyuan">
            <img src="../../../static/cooperation/process/process-4.png" alt="">
            <p class="font-20 margin-top-25 margin-bottom-18">产品入门培训</p>
            <span class="font-14">一对一培训</span>
          </div>
          <div class="process inline-block color-cameo font-siyuan">
            <img src="../../../static/cooperation/process/process-5.png" alt="">
            <p class="font-20 margin-top-25 margin-bottom-18">业务开展</p>
            <span class="font-14 margin-bottom-7">三大服务体系</span>
            <p class="font-14">十一项服务保障</p>
          </div>
        </div>
        <!--按钮-->
        <!--<div class="apply font-16 color-cameo font-siyuan">-->
        <a class="apply font-16 color-cameo font-siyuan" href="/join.html" tag="div">立即申请</a>
        <!--</div>-->
      </div>
    </f-module>
    <!--加盟流程 end-->
    <!--年入百万计划 start-->
    <f-module class="million">
      <div class="section type-page text-center padding-top-90">
        <!--模块标题部分-->
        <div class="font-xi">
          <p class="font-34 color-2121"><i class="line"></i><span class="margin-left-24 margin-right-24">年入百万计划</span><i
            class="line"></i></p>
          <p class="font-20 color-cameo margin-top-10">多渠道收入，<span class="font-lan">高佣金分润</span>，让代理商收入更多更持久</p>
        </div>
        <div class="million-plan">
          <!--计划盒子-->
          <div class="plann-box text-left">
            <!--盒子左边-->
            <div class="box-left inline-block">
              <!--定制开发-->
              <div>
                <div class="box-icon font-0 ver-align-m">
                  <img src="../../assets/images/cooperation/plan/plan-1.png" alt="">
                </div>
                <div class="box-word font-0 ver-align-m">
                  <h4 class="font-18 margin-bottom-15">定制开发</h4>
                  <p class="font-14 font-siyuan color-cameo">
                    付呗拥有稳定的系统软件以及强大的技术团队，针对代理商的一些大型客户的定制开发需求，我们会优先满足，并且提供对应的解决方案和技术支持</p>
                </div>
              </div>
              <!--机具盈利-->
              <div class="profit">
                <div class="box-icon font-0 ver-align-m">
                  <img src="../../assets/images/cooperation/plan/plan-2.png" alt="">
                </div>
                <div class="box-word font-0 ver-align-m margin-left-10">
                  <h4 class="font-18 margin-bottom-15">机具盈利</h4>
                  <p class="font-14 font-siyuan color-cameo">
                    代理商可从我们这里低价买进，高价卖出，赚取中间差价。如POS机，市场在1200-1500左右，一年签500个商家，大概会卖出100个POS，即：100*620=6.2万</p>
                </div>
              </div>
              <!--自媒体推广-->
              <div>
                <div class="box-icon font-0 ver-align-m margin-left-10">
                  <img src="../../assets/images/cooperation/plan/plan-3.png" alt="">
                </div>
                <div class="box-word font-0 ver-align-m margin-left-15">
                  <h4 class="font-18 margin-bottom-15">自媒体推广</h4>
                  <p class="font-14 font-siyuan color-cameo">
                    代理商可以搭建一个本地化的生活服务类平台，通过微信公众号或者服务窗聚集粉丝，吸引商家入驻，给商家在平台群发优惠券，类似腾讯新闻一样，赚取广告费用，按照500家商家，每个月广告费300元，一个月300*16=14800元，一年12*4800=5.16万</p>
                </div>
              </div>
            </div>
            <!--盒子右边-->
            <div class="box-right inline-block ver-align-t margin-left-66">
              <!--佣金分润-->
              <div>
                <div class="box-icon font-0 ver-align-m">
                  <img src="../../assets/images/cooperation/plan/plan-4.png" alt="">
                </div>
                <div class="box-word font-0 ver-align-m">
                  <h4 class="font-18 margin-bottom-15">佣金分润</h4>
                  <p class="font-14 font-siyuan color-cameo">
                    所有签订的商家，收银的手续费为0.3%全返给代理商，一年签约500个商家，每天每个商家平均扫码支付金额1000元，每天的分润即：1000*0.003*500=1500元；一个月1500*30=45000元；一年1500*365=547500元</p>
                </div>
              </div>
              <!--区域发展受理商-->
              <div class="area-develop">
                <div class="box-icon font-0 ver-align-m margin-right-45">
                  <img src="../../assets/images/cooperation/plan/plan-5.png" alt="">
                </div>
                <div class="box-word font-0 ver-align-m ">
                  <h4 class="font-18 margin-bottom-15">区域发展受理商</h4>
                  <p class="font-14 font-siyuan color-cameo">
                    按照付呗全国市代统一价格1万。平均每个月发展3家受理商。一年按照10个月算。即3*1*10=30万</p>
                </div>
              </div>
              <!--增值服务-->
              <div class="margin-bottom-10">
                <div class="box-icon font-0 ver-align-m margin-right-45">
                  <img src="../../assets/images/cooperation/plan/plan-6.png" alt="">
                </div>
                <div class="box-word font-0 ver-align-m">
                  <h4 class="font-18 margin-bottom-15">增值服务</h4>
                  <p class="font-14 font-siyuan color-cameo">付呗点睛、付呗贷等，付呗贷帮助商家信用贷款收取5%-10%的手续费(200万x5%=10万)，投放朋友圈广告赚50%差价与返佣以一年发展500个商家来算，一年收入约97元+其他增值服务在20万左右=117万元左右</p>
                </div>
              </div>
            </div>
          </div>
          <!--按钮-->
          <!--<div class="apply font-16 color-cameo font-siyuan">-->
          <a class="apply font-16 color-cameo font-siyuan" href="/join.html" tag="div">立即申请</a>
          <!--</div>-->
        </div>
      </div>
    </f-module>
    <!--年入百万计划 end-->
    <f-footer></f-footer>
  </div>
</template>
<script>
  import swiper from 'src/mixins/swiper'       //轮播图插件
  import FModule from 'src/components/f-module/index.vue'   //组件
  import IonicBox from 'src/components/x-icon/x-icon.vue'   //小圖標
  import FFooter from 'src/components/f-footer'
  import FHeader from 'src/components/f-header'

  export default{
    mixins: [swiper],
    components: {
      FModule,
      IonicBox,
      FHeader,
      FFooter,
    },
    data(){
      return {}
    }
  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/modules/cooperation.less";
</style>
