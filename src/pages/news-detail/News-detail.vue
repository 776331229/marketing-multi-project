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
      this.id = this.$route.query.id;
      this.getDetail();
    },
    methods:{
      getDetail(){
        let _this = this;
        http.post('/Home/NewIndex/newsInfo',{id:this.id}).then(
          res => {
            if(res.success){
              this.news = res.data;
              console.log(this.news);
            }else {
              console.log(res.message)
            }
          },error => {
            console.log(error);
          }
        )
      }
    }
  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/modules/newDetail";
</style>
