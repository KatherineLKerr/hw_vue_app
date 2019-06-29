<template lang="html">
  <films-list :films="films"></films-list>
</template>
<script>

import FilmsList from '@/components/FilmsList.vue'

export default {
  data() {
    return {
      films: [],
      selectedFilm: null
      }
    },
    components: {
      "films-list": FilmsList
    },
    mounted(){
      fetch('https://ghibliapi.herokuapp.com/films')
      .then(res => res.json())
      .then(films => this.films = films)
    }
  }

</script>

<style lang="css" scoped>
</style>
