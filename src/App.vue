<template>
  <div id="app">
    <transition 
      enter-active-class="slideInRight animated"
      leave-active-class="slideOutRight animated"      
    >
         <router-view class="page"/>
    </transition>   
    <!-- router-view 存放页面 -->
    <div id="nav" class="footer row">
      <router-link to="/" class="col ihome">首页</router-link>  
      <router-link to="/cat" class="col icat">分类</router-link>  
      <router-link to="/cart" class="col icart">购物车</router-link> 
      <router-link to="/user"  class="col iuser">我的</router-link>
      <!-- router-link 切换页面导航 -->
    </div>  
    <!-- <van-tabbar route>
      <van-tabbar-item   to="/" icon="home-o">
    分类
     <img
      slot="icon"
      slot-scope="props"
      :src="props.active ? icon.active : icon.inactive"
    >
  </van-tabbar-item>
  <van-tabbar-item   to="/cat" icon="home-o">
    分类
  </van-tabbar-item>
  <van-tabbar-item   to="/cart" icon="search">
   购物车
  </van-tabbar-item>
    <van-tabbar-item  to="/user" icon="search">
   我的
  </van-tabbar-item>
  
  
</van-tabbar>   -->
  </div>
</template>
 <script>
 export default {
   data(){return {active:0}},
   created(){
     console.log(this.$router)
   }
 }
 </script>
 
<style>
*{margin: 0; padding: 0;}
/* 清零 */
a{text-decoration: none; color: #777;}
/* a 装饰线没有，颜色默认灰色 */
.page{ position: absolute; left:0; right:0; top:0; bottom:.98rem; overflow: auto;background-color: #fff; }
/* 页面固定定位再页面顶部 bottom:49px留出底部栏高度，内容溢出自动 */
.animated{  
  animation-duration: .4s !important;  /* 修改时间 */
}
.slideOutRight{ animation-delay: .4s;filter:brightness(80%)}
#nav{ 
  display: flex; 
  /* 弹性布局 */
  box-shadow: 0 -2px 4px rgba(200,200,200,.4);
  /* 阴影 x y 模糊 颜色值 */
  width: 100%; position: absolute; left:0; right:0; bottom:0; height: .98rem;
  /* 固定再页面底部 高度49 */
   }
#nav a{ 
  flex:1; 
  /* 自适应宽 */
  /* line-height: .98rem;  */
  /* 100px = 1rem; */
  text-align: center;
  /* 垂直水平居中 */
   }
  /* 精确匹配-配置和路由地址完全一致 */
.router-link-exact-active {
  color:#f30;
}
/* a默认灰色，去掉默认的下划线 */
.footer{
  position: fixed;
  left:0;
  right:0;
  bottom:0;
  height: 49px;
  background-color: #f0f0f0;
}
/* 固定定位到底部 高度为49px */
.footer .col{
font-size: 12px; 
/* 设置文字大小 */
display: flex; 
flex-direction: column;
/* 垂直弹性布局 */
justify-content: center; 
/* 垂直居中 */
align-items: center;}
/* 水平居中 */
.footer .col:before{
  content:"";
  /* 伪类 内容为空 */
  display: block;
  height: 22px;
  width: 22px;
  /* 转换为块，设置宽高 */  
  background-image: url("./assets/home.png");
  /* 设置背景图片 */
  background-size: cover;
  /* 设置背景图片大小 覆盖22px */
}
.footer .ihome.router-link-exact-active:before{
  background-image: url("./assets/home-h.png");
}
.footer .icat.router-link-exact-active:before{
  background-image: url("./assets/cat-h.png");
}
.footer .icart.router-link-exact-active:before{
  background-image: url("./assets/cart-h.png");
}
.footer .iuser.router-link-exact-active:before{
  background-image: url("./assets/user-h.png");
}
/* 该元素是.footer 的子元素 同时拥有.col类和.active类 */
.footer .col.router-link-exact-active {
  color:#f30;
}
.footer .icat:before{
   background-image: url("./assets/cat.png");
}
.footer .iball:before{
   background-image: url("./assets/ball.png");
}
.footer .icart:before{
   background-image: url("./assets/cart.png");
}
.footer .iuser:before{
   background-image: url("./assets/user.png");
}
.row{ display: flex; } .col{ flex:1; }
/* .route-link-active  配置 地址和路由配置有部分匹配 */


</style>
