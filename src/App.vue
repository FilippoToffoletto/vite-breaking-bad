<script>
import axios from 'axios';
import {store } from './data/store'

import AppHeader from './components/AppHeader.vue';
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
    CharacterList
  },
  methods:{
    getCharacters(){
      axios.get(store.apiUrl, {
        params:{
          category:store.categoryToSearch
        }
      })
    .then(result => {
      store.charactersListData = result.data;
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
  <CharacterList @startSearch='getCharacters()'/>
</template>



<style lang="scss">
@use './components/styles/general.scss';


</style>