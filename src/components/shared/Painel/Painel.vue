
<template>
  <div class="painel">
    <h2 class="painel-titulo" @dblclick="isVisible = !isVisible"  >{{ titulo }}</h2>
    <div class="painel-conteudo" v-show="isVisible">
      <slot></slot>
    </div>
  </div>
</template>

<script>

export default {
   props: ['titulo'],

   data() {
     return {
       isVisible: true
     }
   }

}

</script>

<style scoped>
  .painel {
    width: 250px;
    height: 300px;
    background-color: #f5f6fa;
    color: #2f3640;
    text-align: center;
  }
</style>
