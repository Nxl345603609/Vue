<template>
	<div>
		<div class="hotlist">
			<ul>
				<li v-for="data in datalist">
					<div class="pic">
						<img :src="`http://img2.97hyg.com${data.thumb}`"/>
						<p>{{data.title}}</p>
					</div>
					<div class="price">
						<p><span>{{data.zongrenshu}}</span>元</p>
					</div>
					<a href="" title="">立即抢购</a>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default {

  name: 'hot',

  data () {
    return {
    	datalist:[]
    }
  },
  mounted(){
  	fetch("/site/listajax",{
      method:'post',
      headers: {
                "Content-Type": "application/x-www-form-urlencoded"
               },
      body:"time=Y&renqi=&shenyurenshu=&zongrenshuup=&zongrenshudown=&pageindex=1&pagesize=10&cateid=0"
    }).then(res=>res.json()).then(res=>{
    	console.log(res.data.list)
    	this.datalist = res.data.list
    });
  }
}
</script>

<style lang="scss" scoped>
	.hotlist{
		ul{
			overflow: hidden;
			li{
				float: left;
				padding:0.2rem 0.2rem;
				list-style: none;
				box-sizing:border-box;
				width:50%;
				border-bottom: 0.02rem solid #d5d5d5;
				border-right: 0.02rem solid #d5d5d5;
				.pic{
					text-align: center;
					img{
						display: block;
						width:2rem;
						height:2rem;
						margin:0.2rem auto;
					}
					p{
					    color: #666666;
					    font-size: 12px;
					    text-align: left;
					    height: 0.64rem;
					    line-height: 0.32rem;
					    margin-bottom: 0;
					    overflow: hidden;
					    text-overflow: ellipsis;
					    display: -webkit-box;
					    -webkit-line-clamp: 2;
					    -webkit-box-orient: vertical
					}
				}
				.price{
					overflow:hidden;
					p{
						width: 80%;
					    font-size: 12px;
					    color: #999999;
					    margin: 0.1rem 0;
					}
				    span{
				    	font-size: 18px;
    					color: #999;
				    }
				}
				a{
					text-decoration: none;
				    display: block;
				    background: #df231c;
				    border-radius: 0.12rem;
				    font-size: 12px;
				    color: #fff;
				    text-align: center;
				    width: 2rem;
				    height: 0.6rem;
				    line-height: 0.6rem;
				    margin: 0 auto;
				}
			}
		}
	}
</style>