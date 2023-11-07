
<template>
  <RouterView />
  <section>
    <h3>Hello, <input type="text" v-model="name"></h3>
  </section>

</template>
  <script setup lang="ts">
  import { RouterLink, RouterView } from 'vue-router'
  import {ref, onMounted, computed, watch } from 'vue'
  
  const todos = ref([])
  //make point to db
  const name = ref('')

  watch(name, () => {
    localStorage.setItem('name', name.value)
  })

  onMounted(() => {
    name.value = localStorage.getItem('name') || ''
  })

  </script>

<style scoped>
</style>
