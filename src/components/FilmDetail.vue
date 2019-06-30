<template lang="html">
  <div class='detail-box'>
    <h3>Film Details:</h3>
    <div v-if="this.film != ''" class="film-detail">
      <h3>{{film.title}}</h3>
      <p>Released in: {{film.release_date}} </p>
      <p>Description: {{film.description}}</p>
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
