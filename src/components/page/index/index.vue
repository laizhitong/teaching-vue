<template>
  <div>
    <header class="header">
    	<div class="back iconfont">&#xe624;</div>
    	<div class="search">
    		<a href="#" class="jump">
    			<i class="iconfont">&#xe86e;</i>
    			<span>输入城市/景点/游玩主题</span>
    		</a>
    	</div>
    	<div class="city">
    		<span>城市</span>
    		<i class="icon iconfont">&#xe79b;</i>
    	</div>
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
		height: .6rem;
		margin: .14rem .18rem;
		background: #fff;
		border-radius: .1rem;
		line-height: .6rem;
	}
	.search .jump{
		display: block;
		color: #e5e7ea;
		font-size: .3rem;
	}
	.search .jump .iconfont{
		font-size: .4rem;
		position: absolute;
		margin-left: .2rem;
	}
	.search .jump span{
		display: inline-block;
		margin-left: .7rem; 
	}

	.city {
		width: 1.14rem;
		line-height: .86rem;
		text-align: center;
	}
	.city span{

	}
	.city .icon{
		font-size: .2rem;
	}

	.swiper-img-con {
		overflow: hidden;
		width: 100%;
		height: 0;
		padding-bottom: 26.55%;
	}
	.swiper-img {
		width: 100%;
	}
</style>