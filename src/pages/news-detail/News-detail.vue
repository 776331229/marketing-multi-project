<template>
  <div>
    <f-header></f-header>
    <f-module>
      <div class="center">
        <div class="center-box">
          <div class="content">
            <h1>{{news.title}}</h1>
            <div class="content-author">
              <span class="recommend">
                <a class="author" href="javascript:void(0)">付小貝</a>
                <a class="aicon hxfwtd" href="javascript:void(0)"></a>
              </span>
              <span class="time recommend">{{news.create_time}}</span>
            </div>
            <div class="contents" v-html="news.content">
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
  import http from 'src/utils/http'

  export default{
    components: {
      FModule,
      FHeader,
      FFooter,
    },
    data (){
      return {
        id:'',
        news:{
          author:'',
          click:'',
          content:'',
          create_time:'',
          id:'',
          img:'',
          title:''
        }
      }
    },
    mounted(){
      this.id = window.location.search.split("=")[1];
      this.getDetail();
    },
    methods:{
      getDetail(){
        let _this = this;
        http.post('/Home/NewIndex/newsInfo',{id:this.id}).then(
          res => {
            this.appShow();
            if(res.success){
              this.news = res.data;
            }else {
              console.log(res.message)
            }
          },error => {
            console.log(error);
          }
        )
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
  @import "./../../assets/css/modules/newDetail";
</style>
