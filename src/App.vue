<template lang="html">
  <div>
    <page-header></page-header>
    <films-list :films="films"></films-list>
    <film-detail v-if="this.selectedFilm != null" :film="selectedFilm"></film-detail>
  </div>
</template>
<script>

import { eventBus } from '@/main.js'
import FilmsList from '@/components/FilmsList.vue'
import PageHeader from '@/components/PageHeader.vue'
import FilmDetail from '@/components/FilmDetail.vue'

export default {
  data() {
    return {
      films: [],
      selectedFilm: null
      }
    },
    components: {
      "films-list": FilmsList,
      "page-header": PageHeader,
      "film-detail": FilmDetail
    },
    mounted(){
      fetch('https://ghibliapi.herokuapp.com/films')
      .then(res => res.json())
      .then(films => this.films = films)

      eventBus.$on('selected-film', (film) => {
        this.selectedFilm = film
      })
    }
  }

</script>

<style lang="css" scoped>
</style>
