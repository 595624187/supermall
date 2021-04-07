<template>
  <div class="goods-item">
    <a :href="item.pcLink">
      <img :src="item.itemImage" alt="">
    </a>
    <div class="goods-info">
      <span>id:{{item.actorId}}</span>
      <span>原价:{{item.orgPrice}}</span>
      <span>售价:{{item.price}}</span>
    </div>

  </div>
</template>

<script>
export default {
  name: "GoodsListItem",
  props:{
    item:{
      type:Object,
      default(){
        return {}
      }
    }
  },
  created(){
    // console.log(this.item)
  }
}
</script>

<style scoped>
.goods-item{
  position: relative;
  width:50%;
}

.goods-item img{
  width:80%;
}
.goods-info{
  padding-bottom: 10px;
}
.goods-info span{
  display:inline-block;
  padding: 10px;
  font-size: 15px;
}
</style>
