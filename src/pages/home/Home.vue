<template>
  <div>
    <f-header></f-header>
    <!--轮播图 start-->
    <div class="swiper-big-box swiper-container">
      <swiper :options="swiperOption" ref="mySwiper" style="width: 100%;" class="swiper-big-box margin-bottom-100">
        <!-- 幻灯内容 -->
        <swiper-slide v-for="item in bannerList" :key="n" class="swiper-box ">
          <div class="swiper-pic swiper-wrapper">
            <a href="/test.html"><img :src="item" alt="banner" style="width: 100%;"></a>
          </div>
          <!--左右按钮-->
        </swiper-slide>
        <div class="swiper-button-prev" slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div>
      </swiper>
    </div>
    <!--轮播图 end-->

    <!--支付样式 start-->
    <f-module class="overflow-hide pay-big-box">
      <!--支付方式-->
      <div class="pay-box ">
        <!--支付描述-->
        <div class="pay-account">
          <!--支付logo-->
          <div class="pay-logo dis-inline-block"></div>
          <span class="dis-block font-siyuan margin-10 font-color" >客户群体全覆盖</span>
          <div class="pay-way dis-inline-block margin-10"></div>
        </div>
        <!--iphone手机样式-->
        <div class="pay-iphone-box dis-inline-block margin-10">
          <div class="pay-case margin-top-40 margin-left-45">
            <!--分模块路由，支付模式 = 二维码收款 App收款 扫码枪收款 pos收款  APi接口-->
            <div class="pay-big-box overflow-hide">
              <!--渲染5个模块-->
              <f-payment :type="active"></f-payment>
            </div>
            <!--支付导航栏-->
            <div class="pay-option">
              <ul class="pay-icon-box dis-inline-block margin-right-10 margin-left-40">
                <li class="font-color"><a :class="{'tab-link':active==1}"  @mouseover="showActive(1)"><i class="qri-coon"></i>二维码收款<i class="line-right"></i></a></li>
                <li class="font-color"><a :class="{'app-link':active==2}" @mouseover="showActive(2)"><i class="app-icon"></i>APP收款<i class="line-right"></i></a></li>
                <li class="font-color"><a :class="{'scan-link':active==3}" @mouseover="showActive(3)"><i class="scan-icon"></i>扫码枪收款<i class="line-right"></i></a></li>
                <li class="font-color"><a :class="{'pos-link':active==4}" @mouseover="showActive(4)"><i class="pos-icon"></i>POS机收款<i class="line-right"></i></a></li>
                <li class="font-color"><a :class="{'api-link':active==5}" @mouseover="showActive(5)"><i class="api-icon"></i>API收款</a></li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </f-module>

    <!--合作伙伴模块 start-->
    <f-module class="part-box">
      <!--合作伙伴描述-->
      <div class="partners-big-box">
        <p class="text-center font-xi font-34 text-note">我们每日帮助超过<span class="font-lan">50万</span>公司处理百万笔交易</p>
        <p class="text-center font-hui font-siyuan font-18 text-note-2">合作伙伴包括 <span class="font-lan">14个商城、6个商业街、5个机场、4个广场、以及50万多家中小商户</span>
        </p>
      </div>
      <!--合作伙伴展示-->
      <div class="shop-box margin-top-60">
        <ul class="dis-inline-block">
          <!--农夫山泉-->
          <li>
            <img src="../../../static/partners/nongfushanquan.png" alt="nongfushanquan" title="nongfushanquan" class="logo-one">
          </li>
          <!--银泰城-->
          <li>
            <img src="../../../static/partners/yintai.png" alt="yintai" title="yintai" class="logo-two">
          </li>
          <!--中央广场-->
          <li>
            <img src="../../../static/partners/shangchang.png" alt="shangchang" title="shangchang" class="logo-three">
          </li>
          <!--新街口-->
          <li>
            <img src="../../assets/images/partners/xinjiekou.png" alt="xinjiekou" title="xinjiekou" class="logo-four">
          </li>
          <!--永旺-->
          <li>
            <img src="../../../static/partners/yongwang.png" alt="yongwang" title="yongwang" class="logo-five">
          </li>
          <!--桂发祥-->
          <li>
            <img src="../../../static/partners/guifaxiang.png" alt="guifaxiang" title="guifaxiang" class="logo-six">
          </li>
          <!--五芳斋-->
          <li>
            <img src="../../../static/partners/wufangzhai.png" alt="wufangzhai" title="wufangzhai" class="logo-seven">
          </li>
          <!--DQ-->
          <li>
            <img src="../../../static/partners/DQ.png" alt="DQ" title="DQ" class="logo-eight">
          </li>
          <!--小飞象-->
          <li>
            <img src="../../../static/partners/xiaofeixiang.png" alt="xiaofeixiang" title="xiaofeixiang" class="logo-nine">
          </li>
          <!--正新鸡排 -->
          <li>
            <img src="../../../static/partners/zhengxinjipai.png" alt="zhengxinjipai" title="zhengxinjipai" class="logo-eleven">
          </li>
          <!--左临右舍-->
          <li>
            <img src="../../../static/partners/zuolin.png" alt="zuolin" title="zuolin" class="logo-twelve">
          </li>
          <!--真功夫-->
          <li>
            <img src="../../../static/partners/zhengongfu.png" alt="zhengongfu" title="zhengongfu" class="logo-thirteen">
          </li>
        </ul>
      </div>
    </f-module>
    <!--合作伙伴模块 end-->

    <!--服务体系模块 start-->
    <f-module>
      <div class="server-big-box">
        <!--服务体系模块描述-->
        <div class="server-note">
          <p class="font-xi size-34 text-center"><span class="font-lan">三大</span>服务体系 <span class="font-lan">十一项</span>服务保障
          </p>
          <p class="font-xi text-center server-note-2">为合作伙伴业务开展保驾护航</p>
        </div>
        <!--服务体系模块展示块-->
        <div class="server-3-box dis-inline-block margin-top-70 font-0">
          <ul class="dis-inline-block">
            <!--日常运营-->
            <li class="margin-right-30">
              <!--日常运营photo-->
              <div class="photo-daily"><img src="../../../static/partners/daily.png" alt=""></div>
              <div class="daily-notes">
                <p class="color-gary font-20 color-gary font-xi margin-top-20">日常运营</p>
                <p class="daily-style-2 font-16 font-xi color-cameo margin-top-15 margin-bottom-10">全场景连接贴心服务</p>
              </div>
            </li>
            <!--技术产品支持-->
            <li class="margin-right-30">
              <!--技术产品支持photo-->
              <div class="photo-daily"><img src="../../../static/partners/technology.png" alt=""></div>
              <div>
                <p class="daily-style font-xi color-gary font-20 margin-top-20">技术产品支持</p>
                <p class="color-cameo font-xi font-16 color-cameo margin-top-15 margin-bottom-10">
                  专业技术研发团队,无缝切合客户所需求的O2O需求</p>
              </div>
            </li>
            <!--业务运营支持-->
            <li>
              <!--业务运营支持photo-->
              <div class="photo-daily"><img src="../../../static/partners/Operation.png" alt=""></div>
              <div class="daily-notes">
                <p class="daily-style font-xi color-gary font-20 margin-top-20">业务运营支持</p>
                <p class="daily-style-2 font-xi font-16 color-cameo margin-top-15 margin-bottom-10">项目顾问式的运营维护能力</p>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </f-module>
    <!--服务体系模块 end-->

    <!--72小时服务支持  start-->
    <f-module>
      <div class="server-service margin-top-100">
        <img src="../../../static/partners/service.png" alt="">
      </div>
    </f-module>
    <!--72小时服务支持  end-->

    <!--服务流程service start-->
    <f-module class="service-box">
      <div class="service-big-box">
        <div class="service-logo dis-inline-block text-center">
          <img src="../../assets/images/partners/serviceflow.png" alt="">
        </div>
        <div class="service-cooperation dis-inline-block  margin-top-60 font-0">
          <!--1、合作签约-->
          <div class="cooperation-box dis-inline-block margin-right-25 ">
            <img src="../../assets/images/partners/1.png" alt="" style="left:107px">
            <ul class="text-center line-height-36">
              <li class="font-xi font-lan font-20">合作签约</li>
              <li class="font-16 font-siyuan margin-top-29">选择合作区域</li>
              <li class="font-16 font-siyuan">对接专属渠道经理</li>
              <li class="font-16 font-siyuan">签订合作协议</li>
            </ul>
            <p class="focus"></p>
          </div>
          <!--2、合作伙伴归档-->
          <div class="cooperation-box dis-inline-block margin-right-25">
            <img src="../../assets/images/partners/2.png" alt="">
            <ul class="text-center line-height-36">
              <li class="font-xi font-lan font-20">合作伙伴归档</li>
              <li class="font-16 font-siyuan margin-top-29">分配合作伙伴账号</li>
              <li class="font-16 font-siyuan">付呗线上培训系统账号</li>
              <li class="font-16 font-siyuan">分配专属服务对接人</li>
            </ul>
            <p class="focus"></p>
          </div>
          <!--3、运营团队对接-->
          <div class="cooperation-box dis-inline-block margin-right-25">
            <img src="../../assets/images/partners/3.png" alt="">
            <ul class="text-center line-height-24">
              <li class="font-xi font-lan font-20">运营团队对接</li>
              <li class="font-16 font-siyuan margin-top-18">蚂蚁金服高级客情专家</li>
              <li class="font-16 font-siyuan">打造专业团队</li>
              <li class="font-16 font-siyuan">精准服务体系</li>
              <li class="font-16 font-siyuan">日常售后专属经理</li>
              <li class="font-16 font-siyuan">区域业务专属市场顾问</li>
              <li class="font-16 font-siyuan">硬件咨询营销物料配发</li>
            </ul>
            <p class="focus"></p>
          </div>
          <!--4、产品入门培训-->
          <div class="cooperation-box dis-inline-block margin-right-25">
            <img src="../../assets/images/partners/4.png" alt="">
            <ul class="text-center line-height-32">
              <li class="font-xi font-lan font-20">产品入门培训</li>
              <li class="font-16 font-siyuan margin-top-27">付呗实战金牌讲师</li>
              <li class="font-16 font-siyuan">一对一培训</li>
              <li class="font-16 font-siyuan">快速了解产品操作</li>
              <li class="font-16 font-siyuan">上手业务开展</li>
            </ul>
            <p class="focus"></p>
          </div>
          <!--5、业务开展-->
          <div class="cooperation-box dis-inline-block">
            <img src="../../assets/images/partners/5.png" alt="">
            <ul class="text-center line-height-32">
              <li class="font-xi font-lan font-20">业务开展</li>
              <li class="font-16 font-siyuan margin-top-27">三大服务体系</li>
              <li class="font-16 font-siyuan">十一项服务保障</li>
              <li class="font-16 font-siyuan">为合作伙伴业务</li>
              <li class="font-16 font-siyuan">开展保驾护航</li>
            </ul>
            <p class="focus"></p>
          </div>
        </div>
      </div>
    </f-module>
    <!--服务流程service end-->

    <!--行业新闻 start-->
    <f-module>
      <div class="news-big-box dis-inline-block text-center margin-bottom-85">
        <!--新闻logo start-->
        <div class="news-logo dis-inline-block text-center">
          <img src="../../assets/images/partners/news.png" alt="news logo" title="news">
        </div>
        <!--新闻logo end-->

        <!--新闻展示详情 start-->
        <div class="news-content dis-inline-block margin-top-70 font-0">
          <!--最新资讯-->
          <div class="news-3 news-message dis-inline-block margin-right-120">
            <a href="#" class="button-box-1"><img src="../../../static/partners/newmessage.png" alt=""></a>
            <ul class="up-to-date padding-left-20 padding-right-20">
              <li v-for="event in industryNews.list"><router-link tag="a" :to="{path:'/news/newsDetail',query:{id:event.id}}">{{event.title}}</router-link></li>
            </ul>
            <div class="news-more margin-top-15 margin-left-174">
              <router-link :to="{path:'/news',query:{type:1}}" tag="p"> <p class="more-style font-siyuan font-12 font-weight-1 line-height-30 margin-right-30 margin-left-15">more<i class="triangle"></i><i class="triangle margin-left-8"></i></p> </router-link>
            </div>
          </div>
          <!--公司动态 start-->
          <div class="news-3 dis-inline-block">
            <a href="#" class="button-box-1"><img src="../../../static/partners/companynews.png" alt=""></a>
            <ul class="up-to-date padding-left-20 padding-right-20">
              <li v-for="item in fubeiNews.list"><router-link tag="a" :to="{path:'/news/newsDetail',query:{id:item.id}}">{{item.title}}</router-link></li>
            </ul>
            <div class="news-more margin-top-15 margin-left-174">
              <router-link :to="{path:'/news',query:{type:2}}" tag="p"> <p class="more-style font-siyuan font-12 font-weight-1 line-height-30 margin-right-30 margin-left-15">more<i class="triangle"></i><i class="triangle margin-left-8"></i></p></router-link>
            </div>
          </div>
        </div>
        <!--新闻展示详情 end-->
      </div>
    </f-module>
    <!--行业新闻 end-->
    <f-footer></f-footer>
  </div>
</template>

<script>
  import swiper from 'src/mixins/swiper'       //轮播图插件
  import FPayment from 'src/components/f-payment/index.vue'
  import banner1 from './../../../static/banner/banner1.png'
  import banner2 from './../../../static/banner/banner2.png'
  import banner3 from './../../../static/banner/banner3.png'
  import banner4 from './../../../static/banner/banner4.png'
  import FModule from 'src/components/f-module/index.vue'
  import FFooter from 'src/components/f-footer'
  import FHeader from 'src/components/f-header'
  import http from 'src/utils/http'
  export default {
    mixins: [swiper],
    components: {
      FModule,
      FPayment,
      FHeader,
      FFooter,
    },
    data () {
      return {
        active:1,   //付款码显示
        n:1,      //图片的index
        industryNews:'',  // 行业动态
        fubeiNews:'' , //付呗动态
        loop: true,     //循环
        bannerList:[
          banner1,
          banner2,
          banner3,
          banner4
        ]
      }
    },
    mounted(){
      let _this = this;
      http.post('/Home/NewIndex/news',{limit:4}).then(
        res => {
          if(res.success){
            _this.industryNews = res.data[0];
            _this.fubeiNews = res.data[1];
          }else {
            console.log(res.message);
          }
        },error => {
          console.log(error);
        }
      )
    },
    methods:{
      showActive(index) {
        this.active = index;
        console.log(this.active);
      }
    }
  }

</script>

<style lang="less" scoped>
  #app{
    overflow-x: hidden;
  }
  @import "../../assets/css/modules/home.less";
</style>
