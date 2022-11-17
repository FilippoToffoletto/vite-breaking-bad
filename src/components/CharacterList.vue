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
    <div class="select-button">
        
        <div class="dropdown">
            <select name="selection" aria-label="" type="button" class="btn btn-secondary dropdown-toggle">
                <option selected>Select Category</option>
                <option value="1">uno</option>
                <option value="2">due</option>
                <option value="3">tre</option>
            </select>
            
        </div>

    </div>
    <div class="ft-container">
        <div class="ft-row">
            <div class="result">
                <h4>Found {{store.charactersListData.length}} characters</h4>
            </div>
        </div>
        <div class="row">
            <CharacterCard 
            v-for="character in store.charactersListData" 
            :key="character.id"
            :character="character"
            />
        </div>
        

    </div>
</main>
</template>


<style lang="scss" scoped>
@import './styles/partials/variables'; 


.ft-container{
    padding: 20px 30px;
    margin:30px auto;
    max-width: 1200px;
    width: 100vw;
    background-color: white;
    .row{
        width: 90%;
        margin: 0 auto;
    }
    .ft-row{
        width: 100%;
    }
}

.result{
    background-color: black;
    margin: 10px 0px;
    padding: 5px 10px;
    display: flex;
    align-items: center;
    h4{
        font-weight: 700;
        font-size: 1.5rem;
    }
}

.select-button{
    margin: 0 auto;
    max-width: 1200px;
}

</style>