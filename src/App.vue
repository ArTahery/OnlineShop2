<script setup>
import { RouterLink, RouterView } from 'vue-router'
import DefaultLayout from './layouts/DefaultLayout.vue'
import HomeViewVue from './views/HomeView.vue'
</script>

<template>
<v-app id="app">
<DefaultLayout></DefaultLayout>
<v-main>
<RouterView/>
</v-main>
</v-app>
  
</template>

<style scoped>

</style>
