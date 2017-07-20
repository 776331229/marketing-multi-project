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
              <a href="/home.html" class="homeLink" title="首页">首页</a>
            </li>
            <li>
              <router-link to="/product" tag="a" title="产品介绍">产品介绍</router-link>
            </li>
            <li>
              <router-link to="/scanPay" tag="a" title="扫码支付">扫码支付</router-link>
            </li>
            <li><router-link to="/cooperation" tag="a" title="加盟合作">加盟合作</router-link></li>
            <li><router-link to="/success-case" tag="a" title="成功案例">成功案例</router-link></li>
            <li><router-link :to="{path:'/news',query:{type:0}}" tag="a" title="最新资讯">最新资讯</router-link></li>
            <li><router-link to="/contact" tag="a" title="联系我们">联系我们</router-link></li>
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

       }
     }
  }
</script>
<style lang="less" scoped>
  @import "index.less";
</style>
