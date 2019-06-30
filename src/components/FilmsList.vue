<template lang="html">
  <div class="filmslist">
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

</style>
