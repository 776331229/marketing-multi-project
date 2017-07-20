<template>
	<div class="edit">
		我是测试页面
  </div>
</template>
Edit
<script>
require('../../assets/css/common.css')

import Top from '../../components/Top'

export default {
  name: 'edit',
  components: {
    Top
  },
  data(){
  	return {

  	}
  }
}
</script>

<style lang="less" scoped>
.edit{
 .box-card{
 	width: 800px;
 	margin: 20px auto;

    .from-group{
      margin:20px 0;
    }
 }
}
</style>
