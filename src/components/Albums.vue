<template>
  <div id="container-cards">
      <Album v-for="card,i in cards" :key="i" :details="card"/>
  </div>
</template>

<script>
import Album from './Album.vue'
import Axios from 'axios'

export default {
  name: 'Albums',
   components: {
    Album
  },
  data() {
      return {
        cards: []
      }  
  },
  created () {
     this.getelement() 
  },
  methods: {
      getelement(){
          Axios
          .get('https://flynn.boolean.careers/exercises/api/array/music')
          .then((result) => {
              this.cards = result.data.response
          })
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#container-cards {
    display: flex;
    flex-wrap: wrap;
    margin: 0 auto;
    width: 70%;
}
</style>