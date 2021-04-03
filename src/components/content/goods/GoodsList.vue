<template>
  <div class="goods">
    <goods-list-item v-for = "item in goods" :item="item">
    </goods-list-item>
  </div>
</template>

<script>
import GoodsListItem from './GoodsListItem'

export default {
  name: "GoodsList",
  props:{
    goods:{
      type:Object,
      default(){
        return {}
      }
    }
  },
  created(){
    console.log(this.goods[0])
  },
  components:{
    GoodsListItem
  }
}
</script>

<style scoped>
.goods{
  display:flex;
  flex-wrap:wrap;
}
</style>
