<template>
<div>
  <Filtergenere @search="sceltagenere()"/>
  <div id="container-cards">
      <Album v-for="card,i in filtercards" :key="i" :details="card"/>
  </div>
</div>
</template>

<script>
import Album from './Album.vue'
import Filtergenere from './Filtergenere.vue'

import Axios from 'axios'

export default {
  name: 'Albums',
   components: {
    Album,
    Filtergenere
  },
  data() {
      return {
        cards: [],
        scelta: "all"
      }  
  },
  created () {
     this.getelement() 
  },
  computed: {
     filtercards(){
       if (this.scelta === "all") {
         return this.cards
       }
       return this.cards.filter((item) => {
         return item.genre.toLowerCase().includes(this.scelta.toLowerCase())
       })
     } 
  },
  methods: {
      getelement(){
          Axios
          .get('https://flynn.boolean.careers/exercises/api/array/music')
          .then((result) => {
              this.cards = result.data.response
          })
      },

      sceltagenere(event) {
          this.scelta = event.target.value
          console.log(this.scelta);
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