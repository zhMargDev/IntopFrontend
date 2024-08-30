<template>
  <HeaderLayout></HeaderLayout>
  <router-view/>
</template>

<script>
import HeaderLayout from '@/layouts/HeaderLayout.vue'

export default{
  components:{
    HeaderLayout
  }
}
</script>

<style>
body, p, h1, h2, h3, h4, h5, h6, span, a, li, td, th, label, input, textarea, button {
  /* Снандартный шрифт для всех текстовых тегов */
  font-family: 'Inter', sans-serif;
  margin: 0;
}
body{
  /* Убираем отступы с body */
  margin: 0;
  padding: 0;
}
</style>
