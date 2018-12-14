<template>
  <div>
    <header>
      <div class="left">
        <a href="/home"><img src="http://img1.97hyg.com/mobile/images/logo.png"/></a>
      </div>
        <i class="iconfont icon-search"></i>
    </header>
    <swipe class="my-swipe">
      <swipe-item><img src="http://img2.97hyg.com/system/lunbo/20170921174811_32856.png"/></swipe-item>
      <swipe-item><img src="http://img2.97hyg.com/system/lunbo/20170921174811_32856.png"/></swipe-item>
      <swipe-item><img src="http://img2.97hyg.com/system/lunbo/20170921174811_32856.png"/></swipe-item>
    </swipe>

    
    <nav>
      <ul>
      <li><i class="you"></i><p>优选商品</p></li>
      <li><i class="shai"></i><p>晒单</p></li>
      </ul>
    </nav>

    <div class="gonggao">
        <div class="pic">
          <img src="http://img1.97hyg.com/mobile/images/ggv2_1.png"/>
        </div>
        <div class="user">
          <a>用户<span>153****4589</span>【2天前】购买了京东E卡经典卡100面值...</a>
        </div>
    </div>

    <div class="navlist">
        <ul>
          <router-link to="/home/hot" tag="li" activeClass="first">人气</router-link>
          <router-link to="/home/newlist" tag="li" activeClass="first">最新</router-link>
        </ul>
          <router-view></router-view>        
    </div>

    <shuoming></shuoming>

    <footnav></footnav>
  </div>
</template>

<script>
import "vue-swipe/dist/vue-swipe.css"; //css 模块化 导入
import { Swipe, SwipeItem } from 'vue-swipe';
import footnav from "@/components/common/footnav"
import shuoming from "@/components/common/shuoming"
export default {

  name: 'home',

  data () {
    return {

    }
  },
  components:{
    footnav,
    swipe:Swipe,
    "swipe-item":SwipeItem,
    shuoming
  }
}
</script>
<style src="@/assets/iconfont/iconfont.css"></style>
<style lang="scss" scoped>
  header{
    z-index:2;
    width:100%;
    height:1rem;
    background:#df231c;
    position: fixed;
    left:0;
    top:0;
    .left{
      float: left;
      margin:0.2rem 0 0 0.2rem;
      img{
        display: block;
        height: 0.7rem;
      }
    }     
    .icon-search{
      float:right;
      padding:0.2rem 0.4rem 0 0;
      color: #fff;
      font-size: 28px;
      font-weight:700;
      }
  }
 .my-swipe{
  position:relative;
  margin-top:1rem;
  width:100%;
  height:2.8rem;
  img{
    width:100%;
    height:2.8rem;
    display:block;
  }
 }
 nav{
  padding:0.18rem 0;
  border-top:0.01rem solid #d5d5d5;
  border-bottom:0.01rem solid #d5d5d5;
  ul{
    display:flex;
    font-size: 14px;  
    li{
      flex:1;
      text-align: center;
      height:1.8rem;
      list-style:none;
      margin-top:0.2rem;
      p{
        height:0.5rem;
        line-height: 0.5rem;
      }
      .you{
        display:inline-block;
        width:0.8rem;
        height:0.8rem;
        background:url(../assets/v2_1_quick.png) no-repeat;
        background-size:163px 40px;
      }
      .shai{
        display:inline-block;
        width:0.8rem;
        height:0.8rem;
        background:url(../assets/v2_1_quick.png) no-repeat;
        background-size:163px 40px;
        background-position:-82px 0px;
      }
    }
  }
 }

 .gonggao{
    width:100%;
    padding:0.3rem 0;
    border-bottom:0.2rem solid #f7f7f7;
    font-size: 12px;
    overflow: hidden;
    .pic{
      float:left;
      padding-left:0.2rem;
      img{
        width:0.36rem;
        height:0.36rem;
      }
      
    }
    .user{
      float:left;
      a{
        padding:0 0.2rem;
      }
    }
 }
 .navlist{
    ul{
      display:flex;
      font-size: 14px;
      color:#2c2c2c;
      li{
        flex:1;
        list-style:none;
        text-align: center;
        height:0.9rem;
        line-height:0.9rem;       
      }
    }
 }

/* .first{
          display:inline-block;
          width:0.2rem;
          height:0.86rem;
          border-bottom:0.04rem solid #df231c;
        } */
</style>