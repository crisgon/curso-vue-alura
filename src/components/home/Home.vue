<template>
  <div>
    <h1>{{ siteTitle }}</h1>

    <input class="search" placeholder="Search Photos" @input="filter = $event.target.value">

    <ul class="list">
      <li class="list-item" v-for="foto in filterPhotos">
        <painel :titulo="foto.titulo">
          <image-responsiva :url="foto.url" :titulo="foto.titulo"/>
        </painel>
      </li>
    </ul>
  <h2> {{ filter }}</h2>
  </div>
</template>

<script>
import Painel from '../shared/Painel/Painel.vue';
import ImagemResponsiva from '../shared/Image-responsiva/ImagemResponsiva.vue';
export default {
  components: {
    'painel': Painel,
    'image-responsiva': ImagemResponsiva
  },

  data () {
    return {
      siteTitle: 'Alura Photos',
      fotos: [],
      filter: ''
    }
  },

  computed: {
    filterPhotos() {
      if(this.filter) {
        let regFilter = new RegExp(this.filter.trim(), 'i');
        return this.fotos.filter(foto => regFilter.test(foto.titulo));
      }

      return this.fotos;
    }
  },

  created() {
    this.$http.get('http://localhost:3000/v1/fotos')
        .then(res => res.json())
        .then(fotos => this.fotos = fotos, err => console.log(err));
  }
}
</script>

<style scoped>
  .list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
  }

  .list-item {
    margin: .5em 0;
    list-style: none;
  }

  .search {
    width: 100%;
    padding: .5em 0;
    margin: .5em 0;
  }
</style>
