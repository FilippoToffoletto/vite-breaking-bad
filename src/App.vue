<script>
import axios from 'axios';
import {store } from './data/store'

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import CharacterList from './components/CharacterList.vue';

export default {
  name:'App',
  data(){
    return{
      store
    }
  },
  components:{
    AppHeader,
    AppMain,
    CharacterList
  },
  methods:{
    getCharacters(){
      axios.get(store.apiUrl)
    .then(result => {
      console.log(result.data)
    })
    .catch(error => {
      console.log(error)
    })
    }
  },
  mounted(){
    this.getCharacters();
  }
}
</script>
<template>
  <AppHeader/>
  <AppMain/>
</template>



<style lang="scss">
@use './components/styles/general.scss';


</style>