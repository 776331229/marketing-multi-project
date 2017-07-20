<template>
  <div>
    <f-header></f-header>
    <f-module>
      <div class="cards-box type-page margin-bottom-20 clearfix">
        <!--卡片-->
        <div class="card" v-for="info in infoList">
          <a :href="'news-detail.html?id='+info.id">
            <img :src="info.img" alt="圖片">
            <h3 class="font-16 card-title">{{info.title}}</h3>
            <p class="card-content"  v-html="info.content"></p>
            <div class="auth-info">
              <div class="name-time inline-block">
                <!--<i class="icon labels"></i>-->
                <span class="name ver-align-m">{{info.author}}</span>
                <span class="ver-align-m">{{info.create_time}}</span>
              </div>
              <div class="chat inline-block">
                <i class="icon2 labels margin-right-10 ver-align-m"></i>
                <span class="ver-align-m">{{info.click}}</span>
              </div>
            </div>
          </a>
        </div>
        <p v-if="!infoList" class="tips">暂无更多新闻！</p>
      </div>
    </f-module>
    <!--页码-->
    <p-nation :page-no="pageNo" :current="currentPage" @change-page="currentPage = $event"></p-nation>
    <f-footer></f-footer>
  </div>
</template>
<script>
  import FModule from 'src/components/f-module/index.vue'   //组件
  import FFooter from 'src/components/f-footer'
  import FHeader from 'src/components/f-header'
  import PNation from 'src/components/pagenation/pagenation.vue'
  import http from 'src/utils/http'
  export default{
    components: {
      FModule,
      PNation,
      FHeader,
      FFooter,
    },
    watch: {
      currentPage: 'requestData'
    },
    ready(){
      this.requestData()
    },
    data(){
      return {
        pageNo: 5,
        currentPage: 1,
        infoList:'', // 新闻列表
        newsData:{
          page:'1',
          limit:'9',
          type:'0'
        }
      }
    },
    mounted(){
      this.newsData.type = window.location.search.split("=")[1];
      this.requestData();
    },
    methods: {
      requestData(){
        this.newsData.page=this.currentPage;
        http.post('/Home/NewIndex/newsList', this.newsData).then(
          res => {
            if(res.success){
              this.infoList = res.data.list;
              let num =  Math.ceil(res.data.count/9);
//                let num = 7;
              this.pageNo = num;
            }else {
              console.log(res.message);
            }
          }, error => {
            console.log(error);
          }
        )
      }
    }
  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/modules/news.less";
</style>
