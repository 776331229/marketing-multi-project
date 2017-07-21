<template>
  <div>
    <f-header></f-header>
    <f-module>
      <div class="map type-page">
        <div id="container" style="width: 100%;height: 500px;"></div>
        <div class="contact">
          <div class="phone inline-block">
            <div class="inline-block phone-big-box">
              <img src="../../assets/images/icon/contact_phone.png" alt="" class="phone-logo">
            </div>
            <div class="inline-block margin-left-20">
              <p class="font-24 font-siyuan">电话: 0571-88533296</p>
            </div>
          </div>

          <div class="address inline-block margin-left-120">
            <div class="inline-block address-big-box">
              <img src="../../assets/images/icon/contact_adress.png" alt="">
            </div>
            <div class="inline-block margin-left-20">
              <p class="font-24 font-siyuan">地址: 杭州市余杭区良渚街道勾庄路218号亿丰时代大厦13楼</p>
            </div>
          </div>
        </div>
      </div>
    </f-module>
    <f-footer></f-footer>
  </div>
</template>

<script>
  import FModule from 'src/components/f-module/index.vue'   //组件
  import FFooter from 'src/components/f-footer'
  import FHeader from 'src/components/f-header'
  export default{
    components:{
      FModule,
      FHeader,
      FFooter,
    },
    data(){
      return {}
    },
    mounted() {
        this.appShow();
        this.loadMap()
    },
    methods:{
      //获取地图经纬度
      loadMap() {
        let map = new AMap.Map('container', {
          resizeEnable: true,
          zoom:16,
          center: [120.063154,30.362742]
        });
        AMap.plugin(['AMap.ToolBar','AMap.Scale'],function () {
          map.addControl(new AMap.ToolBar())
          map.addControl(new AMap.Scale())
        });
        let marker = new AMap.Marker({
          position: [120.063154,30.362742],
          title: '背景',
          color:'red',
          map: map
        });
      },
      /**
       * 初始加载时候的loading动画
       * */
      appShow() {
        const END_TIME = new Date().getTime() //结束时间
        const diffTime = END_TIME - PAGE_START_TIME
        const timer = setTimeout(() => {
          clearTimeout(timer)
          document.querySelector('#loading').className += ' app-loading-hide'
        }, diffTime > 1000 ? 0 : 1000 - diffTime)
      }


    }
  }
</script>
<style lang="less" scoped>
  @import "../../assets/css/index.less";
</style>
<style lang="less" scoped>
  .map{
    padding-top:20px;
  }
  .contact{
    height: 52px;
    padding: 40px 0 30px 50px;
  }
  .phone{
    width:285px;
    position: relative;
  }
  .phone-big-box {
    position: absolute;
    top:3px;
    left: -25px;
  }

  .address {
    width:647px;
    position: relative;
  }

  .address-big-box {
    position: absolute;
    left: -15px;
  }

</style>
