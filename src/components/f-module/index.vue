<template>
 <div class="f-module-box" :style="">
   <section>
     <slot></slot>
   </section>
 </div>
</template>
<script>
  export default {
     data() {
       return {

       }
     },
    props:{
       backgroundImg : ''
    }
  }
</script>
<style lang="less" scoped>
  @import "index.less";
</style>
