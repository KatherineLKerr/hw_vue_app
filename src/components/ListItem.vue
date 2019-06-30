<template lang="html">
  <div>
    <li v-on:click="handleClick">
      <div v-bind:class="{ has_watched: has_watched }">{{ film.title }}</div>
      <div>Watched: <button v-on:click="handleClickButton"> {{ has_watched }} </button> </div>
    </li>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-item',
  data() {
    return {
      has_watched: false
    }
  },
  props: ['film'],
  methods:{
    handleClick(){
      eventBus.$emit('selected-film', this.film)
    },
    handleClickButton(){
      this.has_watched = !(this.has_watched)
    }
  }
}

</script>

<style lang="css" scoped>

  li.has_watched{

  }

  li{
    padding: 10px;
    list-style: none;
    width: 350px;
    display: flex;
    justify-content: space-between;
  }

  li:hover{
    background-color: lightgrey;
  }

  div.has_watched{
    text-decoration: line-through;
  }

  button{
    width: 50px;
  }

</style>
