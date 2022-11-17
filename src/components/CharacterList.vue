<script>
import {store} from '../data/store';
import CharacterCard from './CharacterCard.vue';
  export default {
    name:'CharacterList',
    components:{
        CharacterCard
    },
      data(){
        return{
         store
        }
      }
    
    }
</script>
<template>
<main>
    <div class="container">
        <CharacterCard 
            v-for="character in store.charactersListData" 
            :key="character.id"
            :character="character"/>
    </div>
</main>
</template>


<style lang="scss" scoped>



</style>