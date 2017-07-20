<template>
  <div class="apply-form module-bg-blue">
    <div class="apply-content">
      <div class="top">
        <a href="/home/index/join">
          <img src="../../assets/images/apply/logo.png" alt="" class="fubei-logo">
        </a>
        <img src="../../../static/apply/fubei-wechat.png" class="right">
      </div>
      <!--申请表-->
      <div class="table">
        <h3 style="font-size: 24px;" class="font-lan font-xi">申请加盟表</h3>
        <div id="myform" class="my-form">
          <div class="label">
            <span class="span">公司名称：</span>
            <input type="text" name="company_name" id="company_name" @blur="checkCompany()"
                   v-model="applyData.company_name" placeholder="请输入公司名称">
            <p :class="{'font-lan':outfouceN}" class="regInfo inline-block">
              {{isCompany}}
            </p>
          </div>
          <div class="label">
            <span class="span">所属行业：</span>
            <select name="profession" class="profession" v-model="applyData.profession" @blur="outfouceWork=true">
              <option value selected>请选择</option>
              <option value="情感">情感</option>
              <option value="数码">数码</option>
              <option value="娱乐">娱乐</option>
              <option value="IT">IT</option>
              <option value="购物">购物</option>
              <option value="生活">生活</option>
              <option value="服务">服务</option>
            </select>
            <span class="regInfo inline-block">
              <span v-if="applyData.profession== '请选择' &&outfouceWork">所属行业为必填项目必须填写</span>
            </span>
          </div>
          <div class="label">
            <!--地区-->
            <span class="span">地&nbsp;&nbsp;&nbsp;&nbsp;区：</span>
            <!--省-->
            <select v-model="proCode" name="province" id="searchprov" style="margin-right: 7px;width: 78px"
                    @change="proChange($event,1)">
              <option value="0">请选择</option>
              <option :value="city.code" v-for="(city,index) in proList">{{city.name}}</option>
            </select>
            <!--市-->
            <select v-model="cityCode" name="city" id="searchcity" style="margin-right: 7px;width: 78px"
                    @change="proChange($event,2)">
              <option value="0">请选择</option>
              <option :value="city.code" v-for="(city,index) in cityList">{{city.name}}</option>
            </select>
            <!--区-->
            <select name="area" id="searcharea" style="margin-right: 7px;width: 78px" @change="proChange($event,3)">
              <option value="0">请选择</option>
              <option value="index" v-for="(city,index) in areaList">{{city.name}}</option>
            </select>
            <span class="regInfo"></span>
          </div>
          <!--联系人信息-->
          <div class="label">
            <!--联系人名称-->
            <span class="span">联&nbsp;系&nbsp;人：</span>
            <input type="text" name="people" class="people" v-model="applyData.contacts" @blur="peopleShow=true" placeholder="请输入联系人">
            <span class="regInfo">
              <span v-if="applyData.contacts==''&&peopleShow">联系人必须填写</span>
            </span>
          </div>
          <!--手机号码-->
          <div class="label">
            <span class="span">手&nbsp;&nbsp;&nbsp;&nbsp;机：</span>
            <input type="text" name="phone" class="phone" v-model="phone" @blur="phoneShow=true;checkPhone()" placeholder="请输入手机号码">
            <span class="regInfo">
               <span v-if="phone==''&&phoneShow">手机必须填写</span>
               <span v-if="!isPhone&&phoneShow">手机号码无效</span>
            </span>
          </div>
          <!--手机验证码-->
          <div class="label">
            <span class="span">验&nbsp;证&nbsp;码：</span>
            <input type="text" name="code" class="code" v-model="applyData.code">
            <img v-if="codeImg" :src="codeImg" @click="getCode(phone)" alt="验证码" class="verify-img"
                 style="height: 31px;position: relative;top:9px;">
            <span class="regInfo">
              <span v-if="isSure">{{isSure}}</span>
            </span>
          </div>
          <!--提交申请按钮-->
          <button class="btn" :class="isSubmit ? 'btn-limit':'btn-submit'" @click="applyJoin()">{{buttonT}}</button>
        </div>
      </div>
      <p class="cootRight inline-block">
        Copyright © 2014 付呗 - 浙ICP备13030782号-4
      </p>
    </div>
  </div>
</template>
<script>
  import FModule from 'src/components/f-module/index.vue'   //组件
  import http from 'src/utils/http'

  export default{
    components: {
      FModule
    },
    data(){
      return {
        isSubmit:false,
        isSure: '',
        buttonT: '提交申请',
        outfouceN: false,
        outfouceWork:false,
        phoneShow: false,
        peopleShow: false,
        isCompany: '',  // 公司注册信息反馈
        companyStatus:'',  //公司注册状态
        isPhone: true,
        cityList: '',   // 城市列表
        proList: '',   // 省列表
        areaList: '',  // 区列表
        phone: '',  //手机
//        verImg: '',
        proCode: '0', //省的编码 监听
        cityCode: '0',  //市的编码 监听
        province: '',
        city: '',
        area: '',
        applyData: {
          company_name: '',
          address: '',
          profession: '',  // 行业
          phone: '',
          contacts: '',  // 联系人
          code: ''  //验证码
        },
        codeImg:''
      }
    },
    watch: {
      proCode: function (val, oldval) {
        this.getCity(val, 1);
      },
      cityCode: function (val, oldval) {
        this.getCity(val, 2)
      },
      phone: function (val, oldVal) {
        if (val && /^1[3578]\d{9}$/.test(val)) {
          this.getCode(val);
        }
      },
    },
    mounted(){
      let _this = this;
      _this.getCity(0, 0);
    },
    methods: {
      //选择的省
      proChange(event, no){
        let index = event.currentTarget.selectedIndex;
        let val = event.currentTarget.options[index].text;
        switch (no) {
          case 1:
            this.province = val;
            break;
          case 2:
            this.city = val;
            break;
          case 3:
            this.area = val;
            break;
        }
      },
      // 获取省市
      getCity(code, level){
        let _this = this;
        http.post('/Home/NewIndex/getCity', {code: code, level: level}).then(
          res => {
            if (res.success) {
              if (level == 0) {
                _this.proList = res.data;
              } else if (level == 1) {
                _this.cityList = res.data;
              } else {
                _this.areaList = res.data;
              }
            }
          }, error => {
            console.log(error);
          }
        )
      },
      //验证公司
      checkCompany(){
        if(!this.applyData.company_name){
          this.outfouceN=false;
          this.isCompany = '请输入公司名称';
          return;
        }
        this.outfouceN=true;
        http.post('/Home/NewIndex/checkCompany', {company_name: this.applyData.company_name}).then(
          res => {
            if (res.success) {
              this.isCompany = res.data.msg;
              this.companyStatus  =res.data.status;
            } else {
              console.log(res.message);
            }
          }, error => {

          })


      },
//      获取验证码
      getCode(val){
        this.time++;
        this.codeImg = '/api/Home/Index/getVerify?contacts='+val+'&t='+Date.parse(new Date());
      },
      //    验证电话号码
      checkPhone(){
        if (this.phone && !(/^1[3578]\d{9}$/.test(this.phone))) {
          this.isPhone = false;
          return false;
        } else {
          this.isPhone = true;
          return true;
        }
      },
      //  检查申请数据
      checkData(){
        debugger;
        if (this.applyData.company_name == '') {
          alert("公司名称为必填项目，不能为空");
          return false;
        }
        debugger
        if(this.companyStatus!='1'){
          alert("该公司已存在，不能注册");
          return false;
        }
        if (this.applyData.profession == '') {
          alert("所属行业为必填项目，不能为空");
          return false;
        }
        if (this.cityList == '') {
          alert("地区为必填项目，不能为空");
          return false;
        }
        if (this.applyData.contacts == '') {
          alert("联系人为必填项目，不能为空");
          return false;
        }
        return true;
      },
      // 申请加盟
      applyJoin(){
        if (!this.checkData()) {
          return;
        }
        if (!this.checkPhone()) {
          alert('请正确填写电话');
          return;
        }
        this.applyData.phone = this.phone;
        this.applyData.address = this.province + '--' + this.city + '--' + this.area;
        http.post('/Home/NewIndex/join', this.applyData).then(
          res => {
            if (res.success) {
              this.isSubmit = true;
              this.isSure = '';
              this.buttonT = '正在审核中';
            } else {
              alert(res.data.msg);
              this.isSubmit = false;
              this.isSure = res.data.msg;
            }
          }, error => {
            console.log(error);
          }
        )
      }
    },

    /**切入路由之前，获取进入页面所需要的内容
     * @param to 前往的路由参数
     * @param form 哪里来的路由参数
     * @param next 下一步
     * */
//   beforeRouteEnter(to,from,next){
//       console.log(from.path);
//       if(from.name !== 'checkDetail'){
//           http.post('/localhost:3000/',{}).then(res=>{
//               console.log(res);
//           },error=>{
//               console.log(error);
//           })
//       }
//   }

  }
</script>
<style lang="less" scoped>
  @import "./../../assets/css/modules/join-us.less";
</style>
