<template>
  <button class="botao botao-red" type="tipo" @click="disparaAcao()">{{rotulo}}</button>
</template>

<script>
  export default{
    props: ['tipo', 'rotulo'],

   methods: {
    disparaAcao() {
      if(confirm("Deseja remover?")){
        this.$emit('botaoAtivado');
      }
    }
  }

  }
</script>

<style>
  .botao {
    padding: .5em;
  }

  .botao-red {
    background-color: #e74c3c;
    border: 0;
    color: #fff;
  }
</style>
