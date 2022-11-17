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
      store.charactersListData = result.data
      console.log(store.charactersListData)
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
  <CharacterList />
</template>



<style lang="scss">
@use './components/styles/general.scss';


</style>