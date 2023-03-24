<template>
  <div class="layout">
    <div v-for="item in items" :key="item.id">
      <TodoItem :item="item" />
    </div>
  </div>
</template>

<script setup>
import TodoItem from '@/components/TodoItem.vue'
import ItemService from '@/services/ItemService.js'

import { ref, onMounted } from 'vue'

const items = ref(null)

onMounted(() => {
  ItemService.getTodoItems()
    .then((res) => {
      items.value = res.data
    })
    .catch((error) => {
      console.log(error)
    })

  // axios
  //   .get('http://localhost:3000/items')
  //   .then((res) => {
  //     console.log(res.data)
  //     items.value = res.data
  //   })
  //   .catch((error) => {
  //     console.log(error)
  //   })
})

// const items = reactive([
//   {
//     id: 1,
//     title: 'Vue3学习',
//     date: '2023-03-24',
//     logo: '/src/assets/vue3.png',
//     finished: false,
//   },
//   {
//     id: 2,
//     title: 'Vite学习',
//     date: '2023-03-23',
//     logo: '/src/assets/vite.png',
//     finished: false,
//   },
//   {
//     id: 3,
//     title: 'Pinia学习',
//     date: '2023-03-23',
//     logo: '/src/assets/pinia.png',
//     finished: true,
//   },
//   {
//     id: 4,
//     title: 'Ts学习',
//     date: '2023-03-22',
//     logo: '/src/assets/ts.png',
//     finished: true,
//   },
// ])
</script>

<style scoped>
.layout {
  display: flex;
  flex-wrap: wrap;
  width: 90%;
  margin: 0 auto;
}
.layout div {
  flex: 1;
}
</style>
