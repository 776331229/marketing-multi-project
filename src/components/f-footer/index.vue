<template>
 <div class="">
   <!--页面 底部栏 start  margin-top-60-->
   <footer class="footer-box">
     <div class="foot-top">
       <div class="type-page">
         <div class="left-content inline-block">
           <!--菜单栏 start-->
           <div class="foot-menu font-xi ">
             <router-link :to="{name:'home'}" tag="p" class="font-weight-500">首页</router-link>
             <router-link to="/product" tag="p" class="font-weight-500">产品介绍</router-link>
             <router-link to="/scanPay" tag="p" class="font-weight-500">扫码支付</router-link>
             <router-link to="/cooperation" tag="p" class="font-weight-500">加盟合作</router-link>
             <router-link to="/success-case" tag="p" class="font-weight-500">成功案例</router-link>
             <router-link to="/news" tag="p" class="font-weight-500">最新资讯</router-link>
             <router-link to="/contact" tag="p" class="font-weight-500">联系我们</router-link>
           </div>
           <!--菜单栏 end-->

           <!--合作伙伴 start-->
           <div class="cooperate">
             <p class="">合作伙伴</p>
             <img class="" src="./../../assets/images/home/footer/weixin.png" alt="weixin logo" title="weixin">
             <img class="" src="./../../assets/images/home/footer/alipay.png" alt="alipay logo" title="alipay">
             <img class="" src="./../../assets/images/home/footer/map.png" alt="map logo" title="map">
             <img src="./../../assets/images/home/footer/ali.png" alt="">
           </div>
           <!--合作伙伴 end-->

         </div>
         <div class="right-content inline-block">
           <img class="inline-block" src="../../../static/home/footer/code.png" alt="code logo" title="code">
           <div class="inline-block code_info font-16">
             <p>官方微信号：fubei51</p>
             <p>完美对接支付宝</p>
           </div>
         </div>
       </div>
     </div>

     <!--底部友情链接 start-->
     <div class="footer-bottom type-page text-center">
       <div class="friend_link font-siyuan ">
         <span>友情链接：</span>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
         <p>友情链接</p>
       </div>
       <p class="margin-top30 margin-bottom25 font-16 interPic font-siyuan font-weight-1">网站地图</p>
       <p class="font-14 font-siyuan ">Copyright © 2014 杭州首展科技有限公司 付呗 - 浙ICP备13030782号-4 地址：杭州市余杭区良渚街道勾庄路218号亿丰时代大厦13楼</p>
     </div>
     <!--底部友情链接 end-->

   </footer>
   <!--页面 底部栏 end-->
 </div>
</template>

<style lang="less" scoped>
  @import "index.less";
  @import "./../../assets/css/index.less";
</style>
