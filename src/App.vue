<template>
  <div class="container">
    <menu-princial :rotas="routes"/>
    <transition name="pagina">
    <router-view></router-view>
    </transition>
  </div>
</template>

<script>
import Menu from './components/shared/Menu/Menu.vue';
import { routes } from './routes';

export default {
  components: {
    'menu-princial': Menu
  },

  data() {
    return {
      routes
    }
  }
}
</script>

<style>
  body  {
    background-color: #2f3640;
  }

  .container {
    width: 900px;
    margin: 0 auto;
    text-align: center;
    color: #fff;
  }

  .pagina-enter-active, .pagina-leave-active {
    transition: all .4s;
  }
  .pagina-enter, .pagina-leave-active {
    opacity: 0;
    transform: translateX(-50%);
  }

</style>
