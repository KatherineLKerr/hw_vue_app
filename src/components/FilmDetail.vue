<template lang="html">
  <div class="filmDetail">
    <h3>{{film.title}}</h3>
    <p>Released in: {{film.release_date}} </p>
    <p>Description: {{film.description}}</p>
  </div>
</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']
}
</script>

<style lang="css" scoped>
</style>
