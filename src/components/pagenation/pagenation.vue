<template>
<div class="pager">
  <button class="btn btn-pager"  :disabled="this.current == 1" @click="prePage"> < </button>
  <span v-if="oneShow" class="page-index" :class="1 == current?'active':''" @click="goPage(1)">1</span>
  <span v-if="preClipped" class="page-index">...</span>
  <span v-for="index in pages" class="page-index" :class="index==current?'active':''" @click="goPage(index)">{{index}}</span>
  <span v-if="backClipped" class="page-index">...</span>
  <span class="page-index" :class="pageNo == current?'active':''" @click="goPage(pageNo)">{{pageNo}}</span>
  <button class="btn btn-pager" :disabled="this.current == pageNo" @click="nextPage"> > </button>
</div>
</template>
<script>
  export default{
      props:{
          pageNo:{
              type:Number,
            default:1
          },
        current:{
              type:Number,
          default:1
        }
      },
      data(){
          return{
              backClipped:true,
            preClipped:false,
            oneShow:false
          }
      },
    methods:{
          prePage(){
              console.log(this.current);
              this.$emit('change-page',this.current - 1);
          },
          nextPage(){
            console.log(this.current);
            this.$emit('change-page',this.current + 1);
          },
      goPage(index){
              if(index!==this.current){
                  this.current = index
                this.$emit('change-page',this.current);
              }
      }
    },
    computed:{
          pages:function () {
            let ret = []
            if(this.current>3){
                ret.push(this.current-2)
              ret.push(this.current-1)
            }else {
              for(let i = 1;i<this.current;i++){
                    ret.push(i)
              }
            }
            if(this.current !== this.pageNo){
              ret.push(this.current);
            }
            if(this.current<(this.pageNo-2)){
              this.preClipped = false;
              this.oneShow = false;
                if(this.pageNo>4&&(this.current==1||this.current==2)){
                    for(let i=this.current+1;i<=4;i++){
                        ret.push(i);
                    }
                }else {
                  ret.push(this.current+1)
                }
              if(this.current<=(this.pageNo-3)){
                    this.backClipped = true;
              }
            }else {
                this.backClipped = false;
                if(this.current==(this.pageNo-2)&&this.pageNo>6){
                    this.preClipped = true;
                }
              if(this.current>(this.pageNo-2)&&this.pageNo>6){
                this.oneShow = true;
              }

              for(let i = (this.current+1);i<this.pageNo;i++){
                    ret.push(i);
              }
            }
            return ret
          }
    }
  }
</script>
<style lang="less" scoped>
@import "pagenation.less";
</style>
