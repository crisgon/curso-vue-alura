<template>
  <nav class="menu">
    <ul>
      <li v-for="rota in rotas">
        <router-link :to="rota.path ? rota.path: '/'">{{ rota.titulo }}</router-link>
      </li>
    </ul>
  </nav>
</template>

<script>

  export default {
    props: {
      rotas: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>
  .menu {
    width: 100%;
    height: 50px;
    background-color: #fff;
  }
  ul li{
    display: inline;
  }

  ul li a  {
    color: #000;
    padding: .5em;
  }

</style>
