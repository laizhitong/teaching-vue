<template>
  <div>
    <header class="header">
    	<div class="back">返回</div>
    	<div class="search"></div>
    	<div class="city">城市</div>
    </header>
    <swiper :options="swiperOption">
	    <!-- slides -->
	    <swiper-slide>
	    	<div class="swiper-img-con">
	    		<img class="swiper-img" src="http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg">
	    	</div>
	  	</swiper-slide>
	   <swiper-slide>
	    	<div class="swiper-img-con">
	    		<img class="swiper-img" src="http://img1.qunarzz.com/piao/fusion/1810/af/30ffcf34e9819f02.jpg_750x200_736b7236.jpg">
	    	</div>
	  	</swiper-slide>
	  	<swiper-slide>
	    	<div class="swiper-img-con">
	    		<img class="swiper-img" src="http://img1.qunarzz.com/piao/fusion/1808/70/5603e6a535062402.jpg_750x200_2c552f2c.jpg">
	    	</div>
	  	</swiper-slide>
	  	<swiper-slide>
	    	<div class="swiper-img-con">
	    		<img class="swiper-img" src="http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg">
	    	</div>
	  	</swiper-slide>
	  	<swiper-slide>
	    	<div class="swiper-img-con">
	    		<img class="swiper-img" src="http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg">
	    	</div>
	  	</swiper-slide>
	  	<swiper-slide>
	    	<div class="swiper-img-con">
	    		<img class="swiper-img" src="http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg">
	    	</div>
	  	</swiper-slide>
	    <div class="swiper-pagination"  slot="pagination"></div>

	  </swiper>
  </div>
</template>

<script>
export default {
  name: 'Index',
  data () {
      return {
        swiperOption: {
        	 autoplay:true,
        	 loop : true
          // some swiper options/callbacks
          // 所有的参数同 swiper 官方 api 参数
          // ...
        }
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
		width: 100%;
	}
	.swiper-img {
		width: 100%;
	}
</style>