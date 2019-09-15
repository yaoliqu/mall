<template>
<div class="recomends">
    <div class="recommend-item" v-for="item in recommends" :key="item.id">
        <a :href="item.link">
            <img :src="item.image" alt="">
            <div>{{item.title}}</div>
        </a>
    </div>
</div>
</template>

<script>
export default {
  name: 'HomeRecommends',
  props:{
      recommends:{
          type:Array,
          default(){
              return []
          }
      }
  },
  components:{
    
  }
}
</script>

<style>
.recomends{
 display: flex;
 width: 100%;
 text-align: center;
 font-size: 12px;
 padding: 10px 0 20px;
 border-bottom: 10px solid #eeeeee;   
}
.recommend-item{
    flex: 1;
}
.recommend-item img{
    width: 70px;
    height: 70px;
    margin-bottom: 10px;
}
</style>
