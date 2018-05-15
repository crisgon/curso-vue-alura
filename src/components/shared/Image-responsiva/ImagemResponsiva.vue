<template>
  <img :src="url" :alt="titulo"/>
</template>

<script>
  export default {
    props: ['url', 'titulo']
  }
</script>

<style scoped>
  img {
    max-width: 100%;
  }
</style>

