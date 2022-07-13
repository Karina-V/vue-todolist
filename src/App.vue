<template>
  <MainPage />
</template>

<script>
import { onMounted } from '@vue/runtime-core'
import MainPage from './pages/index.vue'

export default {
  components: {
    MainPage
  },

  stup() {
    onMounted(() => {
      console.log(" b m");
    })
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Yanone+Kaffeesatz:wght@200;300;400;500;600;700&display=swap');

body {
  font-family: 'Yanone Kaffeesatz', sans-serif;
}
</style>