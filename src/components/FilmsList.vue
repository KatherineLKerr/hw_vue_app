<template lang="html">
  <div>
    <ul>
      <list-item v-for="film in films" :film="film"></list-item>
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
