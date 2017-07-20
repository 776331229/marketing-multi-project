<template>
  <div class="icon-box" :style="styles1">
    <div class="money" :style="styles">
      <img :src="src" alt="">
    </div>
  </div>
</template>
<script>
  export default{
      props:{
        width:{
          type:Number,
          default:47
        },
        height:{
            type:Number,
          default:47
        },
        marginRight:{
          type:Number,
          default:30
        },
        marginLeft:{
          type:Number,
          default:0
        },
        src:{
            type:String,
            default:''
        }
      },
      data(){
          return{

          }
      },
    computed:{
          styles(){
              return {
                width:this.width+'px',
                height:this.height+'px'
              }
          },
      styles1(){
              return{
                  marginRight:this.marginRight+'px',
                  marginLeft:this.marginLeft+'px'
              }
      }
    }
  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/index.less";
  .icon-box{
    display: inline-block;
    margin-right: 30px;
  }
  .money{
    display: inline-block;
    width: 47px;
    height: 47px;
  }
</style>
