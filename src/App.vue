<template>
<v-app id="app">
<DefaultLayout></DefaultLayout>
<v-main>
<RouterView/>
</v-main>
</v-app>
  
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
import DefaultLayout from './layouts/DefaultLayout.vue'
</script>

<style scoped>

</style>
