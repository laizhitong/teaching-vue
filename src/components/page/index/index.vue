<template>
  <div>
    <header class="header">
    	<div class="back">返回</div>
    	<div class="search"></div>
    	<div class="city">城市</div>
    </header>
    <swiper :options="swiperOption">
	    <!-- slides -->
	    <swiper-slide v-for="item in swiperInfo" :key="item.id">
	    	<div class="swiper-img-con">
	    		<img class="swiper-img" :src="item.imgUrl">
	    	</div>
	  	</swiper-slide>
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	  <div>
			1231231231
	  </div>
  </div>
</template>

<script>
export default {
  name: 'Index',
  data () {
      return {
      	swiperInfo: [],
        swiperOption: {
        	 autoplay:true,
        	 direction: 'horizontal',
        	 loop:true,
        	 pagination:{
        	 	el:'.swiper-pagination'
        	 }
          // some swiper options/callbacks
          // 所有的参数同 swiper 官方 api 参数
          // ...
        }
      }
    },
    created () {
    	this.getIndexData()
    },
    methods: {
    	getIndexData () {
    		this.$http.get("/static/index.json")
    	  .then(this.handleGetDataSucc.bind(this))
    	},
    	handleGetDataSucc (res) {
    		this.swiperInfo = res.body.data.swiper
    	}
    }
}
</script>

<style scoped>
	.header {
		display: flex;
		background: #05bad5;
		color: #FFF;
	}
	.back {
		width: .64rem;
		line-height: .86rem;
	}
	.search {
		flex: 1;
		margin: .14rem .18rem;
		background: #fff;
		border-radius: .1rem;
	}
	.city {
		width: 1.14rem;
		line-height: .86rem;
		text-align: center;
	}
	.swiper-img-con {
		overflow: hidden;
		width: 100%;
		height: 0;
		padding-bottom: 27%;
	}
	.swiper-img {
		width: 100%;
	}
</style>