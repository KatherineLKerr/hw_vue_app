<template lang="html">
  <div>
    <page-header></page-header>
    <div class="main-container">
      <films-list :films="films"></films-list>
      <film-detail :film="selectedFilm"></film-detail>
    </div>
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
      selectedFilm: ""
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
.main-container{
  display: flex;
  justify-content: space-evenly;
}
</style>
