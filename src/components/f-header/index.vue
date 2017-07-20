<template>
 <div>
   <!--首页导航栏样式  start-->
    <header class="bod-bottom">
      <!--导航大盒子 版心-->
        <div class="type-page j-nav">
          <!--logo样式-->
          <div class="logo-box float-left dis-inline-block"><a href="#" class="dis-inline-block j-logo"></a></div>
          <!--导航菜单栏 start-->
          <ul class=" dis-inline-block float-left font-xi">
            <li>
              <a :class="{'homeLink' : pathName === '/home.html'}" href="home.html" title="首页">首页</a>
            </li>
            <li>
              <a :class="{'homeLink' : pathName === '/product-introduce.html'}" href="product-introduce.html" title="产品介绍">产品介绍</a>
            </li>
            <li>
              <a :class="{'homeLink' : pathName === '/scan-pay.html'}" href="scan-pay.html" title="扫码支付">扫码支付</a>
            </li>
            <li>
              <a :class="{'homeLink' : pathName === '/cooperation.html'}" href="cooperation.html" tag="a" title="加盟合作">加盟合作</a>
            </li>
            <li>
              <a :class="{'homeLink' : pathName === '/successful-case.html'}" href="successful-case.html" tag="a" title="成功案例">成功案例</a>
            </li>
            <li>
              <a :class="{'homeLink' : pathName === '/news.html'}" href="news.html?type=0" tag="a" title="最新资讯">最新资讯</a>
            </li>
            <li>
              <a :class="{'homeLink' : pathName === '/contact.html'}" href="contact.html" tag="a" title="联系我们">联系我们</a>
            </li>
            <li class="float-right" title="联系方式">联系方式 : <span class="font-color-blue">0571-88533296</span></li>
          </ul>
        </div>
    </header>
   <!--首页导航栏样式 end-->
 </div>
</template>
<script>
  export default {
     data() {
       return {
          pathName : '/home.html'
       }
     },
     created(){
       this.pathName =  window.location.pathname;
     }
  }
</script>
<style lang="less" scoped>
  @import "index.less";
</style>
