<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'
import {watch} from 'vue/dist/vue'
import Header from './components/Header.vue'
import Cardlist from './components/CardList.vue'
import driver from './components/driver.vue'


const items = ref([])

onMounted(async () => {
  try {
    const responce = await axios.get('https://c7dab8226ba8ae38.mokky.dev/items')
    const res = [...responce.data[0]]
    items.value = res
  } catch (err) {
    console.log(err)
  }
})

const sortBy = ref ('');
const searchQuery = ref('');

const onChangeSelect = event => {
sortBy.value = event.target.value;
}


watch(sortBy, async ()=> {

  try {
    const responce = await axios.get('https://c7dab8226ba8ae38.mokky.dev/items?sortBy=' + sortBy.value)
    const res = [...responce.data[0]]
    items.value = res
  } catch (err) {
    console.log(err)
  }

});

</script>

<template>
  <!-- <driver /> -->
  <div class="w-4/5 m-auto bg-white rounded-xl shadow-xl mt-14">
  <Header></Header>

    <div class="p-10">
      <div class="flex justify-between items-start">
        <h2 class="text-3xl font-bold mb-10">Все кросовки</h2>

        <div class="flex items-center gap-4">
          <select @change="onChangeSelect"
            name=""
            id=""
            class="py-2 px-3 border border-gray-400 focus:border-gray-600 rounded-md outline-none"
          >
            <option value="name">По названию</option>
            <option value="price">По Цене (дешевле)</option>
            <option value="-price">По Цене (дешевле)</option>
          </select>

          <div class="relative">
            <img
              class="absolute left-3 top-3 cursor-pointer"
              src="/public/search.svg"
              alt="search"
            />
            <input
              placeholder="Search"
              type="search"
              class="border border-gray-400 rounded-md py-2 pl-11 pr-5 outline-none focus:border-gray-600"
            />
          </div>
        </div>
      </div>

      <Cardlist :items="items"></Cardlist>
    </div>
  </div>
</template>
