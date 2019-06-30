<template lang="html">
  <div class="filmslist">
    <h2>List of films:</h2>
    <ul>
      <list-item v-for="(film, index) in films" :film="film" :key="index"></list-item>
    </ul>
  </div>
</template>

<script>

import ListItem from '@/components/ListItem.vue'

export default {
  name: 'films-list',
  props: ['films'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>

  ul{
    list-style-type: none;
    padding: 0px;
  }

</style>
