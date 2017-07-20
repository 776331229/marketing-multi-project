<template>
  <div>
    <div class="box" @click="tap()">
      <slot></slot>
      <!--<div class="left inline-block font-xi">-->
        <!--<h3>{{title}}</h3>-->
        <!--<h5>{{subTitle}}</h5>-->
        <!--<h5>{{subTitleTwo}}</h5>-->
      <!--</div>-->
      <!--<div class="right inline-block">-->
        <!--<img src="../../assets/images/scanPay/scanPay.png" alt="">-->
      <!--</div>-->
    </div>
  </div>
</template>
<script>
  export default{
      props:{
      },
    computed:{

    },
      data(){
          return{}
      },
    methods:{
          tap(){
              console.log('p');
            this.$emit('changeStatus');
          }
    }
  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/index";
  @import "./index";
</style>
