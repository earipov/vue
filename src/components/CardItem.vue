<script setup>
import { inject } from 'vue';

defineProps({
  price: Number,
  title: String,
  imgUrl: String,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function
})





</script>

<template>
  <div
    class="relative border border-slate-100 rounded-3xl p-10 bg-white cursor-pointer hover:-translate-y-2 hover:shadow-xl transition"
  >
    <img
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt=""
      class="absolute top-10 left 10"
      @click="onClickFavorite"
    />
    <img :src="imgUrl" alt="imageUrl" />
    <p class="mt-2">{{ title }}</p>
    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-500">Цена:</span>
        <b>{{ price }} $</b>
      </div>
      <img :src="!isAdded ? '/plus.svg' : '/checked.svg'" alt="checked" @click="onClickAdd" />
    </div>
  </div>
</template>
