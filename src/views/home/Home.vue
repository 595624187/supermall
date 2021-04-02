<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banner="banner"></home-swiper>
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import HomeSwiper from './childComps/HomeSwiper'
import {getHomeMultidata} from 'network/home'

export default {
  name: "Home",
  components:{
    NavBar,
    HomeSwiper
  },
  data(){
    return{
      banner:[],
      recommend:[],
      keywords:[],
      dKeyword:[],
    }
  },
  created(){
    //1.请求多个数据
    getHomeMultidata().then(res=>{
      console.log(res)
      this.banner = res.data.banner.list
      this.recommend = res.data.recommend.list
      this.keywords = res.data.keywords.list
      this.dKeyword = res.data.dKeyword.list
    })
    // console.log(this.result)//不能打印，因为上面函数是异步函数
  }
}
</script>

<style scoped>
.home-nav{
  background-color:var(--color-tint);
  color:#fff;
}
</style>
