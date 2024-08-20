<script setup>
import Card from './CardItem.vue'

defineProps({
  items: Array
})
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      v-for="item in items"
      :key="item.id"
      :title="item.title"
      :price="item.price"
      :imgUrl="item.imageUrl"
       :isFavorite="item.isFavorite"
    />
  </div>
</template>
