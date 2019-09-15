<template>
<div id="home">
<nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
<home-swiper :banners="banners"></home-swiper>
<home-recommends :recommends="recommends"></home-recommends>
<feature-view></feature-view>
<tab-control :titles="['流行','新款','精选']"></tab-control>
<ul>
  <li>1</li>
  <li>1</li>
  <li>a</li>
  <li>1</li>
  <li>a</li>
  <li>a</li>
  <li>a</li>
  <li>a</li>
  <li>a</li>
  <li>a</li>
</ul>
</div>
</template>

<script>
import HomeSwiper from './childcomponnets/HomeSwiper';
import HomeRecommends from './childcomponnets/HomeRecommends';
import FeatureView from './childcomponnets/FeatureView';

import NavBar from 'components/common/navbar/NavBar';
import TabControl from 'components/content/tabControl/TabControl';

import {getHomeMultidata} from 'network/home';
export default {
  name: 'Home',
  components:{
    NavBar,
    HomeSwiper,
    HomeRecommends,
    FeatureView,
    TabControl
  },
  data(){
  return {
   banners:[],
   recommends:[]
  }
  },
  created(){
    //1.请求多个数据
    getHomeMultidata().then(res =>{
      console.log(res);
    this.banners=res.data.banner.list;
    this.recommends=res.data.recommend.list;
    })
  }
}
</script>

<style>
.home-nav{
  background-color: var(--color-tint);
  color: #ffffff;
}
</style>
