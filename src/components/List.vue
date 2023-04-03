<template>
<section>
    <div class="container-row">
      <div id="liste" class="container-wrap" >
        <Character v-for="character in characters" :key="character.id" :character="character"/>
      </div>
    </div>
   
  </section>
</template>

<script>
import axios from 'axios'
import Character from '../components/Character'

export default {
  name: 'List',

  components: {
    Character
  },

  data() {
    return {
      characters:[]
    }
  },

  methods:{
    
      },

  beforeCreate() {
    axios.get(`https://gateway.marvel.com/v1/public/characters?ts=1&apikey=4172741ecf34b2048fcc99cac389bb57&hash=511d95075875ced0eefae83bd69b124b`)
      .then((response) => {this.characters = response.data.data.results;
              console.log(response.data.data.results)})

  }
}
</script>

<style>
.container-row {
  display : flex;
  flex-direction: row;
  justify-content: center;
}

.container-wrap {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: flex-start;
}

#liste{
  width: 1050px;
  height: 1600px;
  margin-top: 50px;
}

</style>
