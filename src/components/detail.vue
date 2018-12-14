<template>
	<div>
		<header>
			<i class="iconfont icon-back"></i>
			<i class="iconfont icon-viewgallery"></i>
		</header>
		<div class="main">
			<swipe class="my-swipe">
		      <swipe-item><img src="http://img2.97hyg.com/system/lunbo/20170921174811_32856.png"/></swipe-item>
		      <swipe-item><img src="http://img2.97hyg.com/system/lunbo/20170921174811_32856.png"/></swipe-item>
		      <swipe-item><img src="http://img2.97hyg.com/system/lunbo/20170921174811_32856.png"/></swipe-item>
		    </swipe>

		    <div class="show">
		    	<p>海飞丝 去屑护肤洗发水200ml</p>
		    	<div class="price">
		    		<p>￥59</p>
		    	</div>
		    </div>
		    <p class="shuoming">特别说明：苹果公司不是好运购赞助商，并且苹果公司也不会以任何形式参与其中！</p>
		    <ul>
		    	<li>图文详情<span>(建议在wifi下查看)</span><i class="iconfont icon-more"></i></li>
		    	<li class="last">晒单评论<i class="iconfont icon-more"></i></li>
		    </ul>		    
		</div>
		<!-- <div class="blank"> 
			
		</div> -->

		<div class="buy">
	    	<div class="buyim">
	    		<p>立即购买</p>
	    	</div>
	    </div>
	</div>
</template>

<script>
import "vue-swipe/dist/vue-swipe.css"; //css 模块化 导入
import { Swipe, SwipeItem } from 'vue-swipe';
import axios from "axios"
export default {

  name: 'new',

  data () {
    return {

    }
  },
  mounted(){
  	console.log(this.$route.params.id)
  	axios.get("/site/listajax").then(res=>{
  	 	console.log(res.data.data.list);
  	 	for(var i = 0;i<res.data.data.list.length;i++){
  	 		if(this.$route.params.id == res.data.data.list[i].shopid){
  	 			console.log(res.data.data.list[i])
  	 		}
  	 	}
  	 })
  },
  components:{
    swipe:Swipe,
    "swipe-item":SwipeItem
  }
}
</script>
<style src="@/assets/iconfont/iconfont.css"></style>
<style lang="scss" scoped>
	header{
		width:100%;
		position: fixed;
		z-index:10;
		top: 0;
		left: 0;
		height: 0.88rem;
		background-color: #f7f7f7;
		overflow:hidden;
		.iconfont{
			font-size:24px;
			z-index:20;
			padding:0.2rem 0.2rem;
			color:#999;
		}
		.icon-back{
			float: left;			
		}
		.icon-viewgallery{
			float:right;
			padding:0.2rem 0.4rem;
		}
	}
	.main{
		width:100%;
		position:relative;
		margin-top:0.88rem;
		background:#f7f7f7;
		.my-swipe{
			width:100%;
			height:4.8rem;
			img{
				width:100%;
				height:4.8rem;
				display: block;
			}
		}
		.show{
			width:100%;
			background:#fff;
			p{
				    color: #2c2c2c;
				    font-size: 14px;
				    width: 94%;
				    margin: 0 auto;
				    display: -webkit-box;
				    display: box;
				    -webkit-line-clamp: 3;
				    -webkit-box-orient: vertical;
				    white-space: normal;
			}
			.price{
				padding:0.3rem 0 ;
				background:#f7f7f7;
				p{
					padding: 0.48rem 3%;
					border-top: 0.04rem solid #df231c;
					background:#fff;
					color:#ff3d00;
					font-weight:bold;
					font-size:17px;
				}
			}
		}
		.shuoming{
			padding:0.1rem;
			width:100%;
			margin:0 auto;
			color:#8f8f94;
			font-size:14px;
		}
		ul{
			width:100%;
			margin-top:0.2rem;
			background:#fff;
			border:0.02rem solid #d5d5d5;
			list-style:none;
			li{
				padding:0.22rem 0.3rem;
				font-size:15px;
				position:relative;
				span{
					font-size:12px;
					color:#999;
				}
				.icon-more{
					position:absolute;
					right:0.4rem;
				}
			}
			.last{
				border-top:0.02rem solid #d5d5d5;
			}
		}
	}
	/* .blank{
		width:100%;
		height:0.88rem;
		background:#f7f7f7;
	} */
	.buy{
		background: #ededed;
	    height:1.02rem;
	   	width:100%;
	    position: fixed;
	    bottom: 0;
	    left: 0;
	    z-index: 100;
	    overflow: hidden;
		.buyim{
			font-size:14px;
			padding:0.2rem 0.2rem;
			background:#df2312;
			text-align: center;
			color:#fff;
			//line-height:1.02rem;
		}
	}
</style>