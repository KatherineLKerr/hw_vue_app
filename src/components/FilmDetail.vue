<template lang="html">
  <div class='detail-box'>
    <div v-if="this.film != ''" class="film-detail">
      <h2>Film Details:</h2>
        <h3>{{film.title}}</h3>
        <p>Released in {{ film.release_date }}</p>
        <p>Description: <br> {{ film.description }} </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']
}
</script>

<style lang="css" scoped>
.detail-box{
  width: 500px;
}
</style>
