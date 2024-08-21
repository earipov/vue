<script setup>
import CardMain from './CardItem.vue'

const emit = defineEmits (['addToFavorite'])



defineProps({
  items: Array,
})
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <CardMain
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :price="item.price"
      :imgUrl="item.imageUrl"
       :isFavorite="item.isFavorite"
       :onClickFavorite="()=> emit('addToFavorite', item)"
    />

  </div>
</template>
