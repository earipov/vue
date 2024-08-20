<script setup>
import driverHover from './driverHover.vue'
import Cartitemlist from './Cartitemlist.vue'
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-10">
    <driverHover></driverHover>

    <Cartitemlist />

    <div class="mb-6 mt-6 flex flex-col gap-4">
      <div class="flex gap-2">
        <span>Itogo:</span>
        <div class="flex-1 border-b border-dashed"></div>

        <b>1290$</b>
      </div>

      <div class="flex gap-2">
        <span>Taks 5%</span>
        <div class="flex-1 border-b border-dashed"></div>

        <b>2000$</b>
      </div>
    </div>
    <button
      disabled=""
      class="bg-line-500 transition w-full hover:bg-lime-600 active:bg-lime-700 cursor-pointer  rounded-xl p-3 bg-lime-500"
    >
      Order
    </button>
  </div>
</template>
