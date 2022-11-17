<script>
export default {
    name:'CharacterCard',
    props:{
        character: Object
    }
}
</script>

<template>
  <div class="ft-card col-3">
    <!-- name, img, category, status -->
        <div class="ft-single-card">
            <div class="img">
                <img :src="character.img" alt="charcter.name">
            </div>
            <div class="card-text">
                <h3>{{character.name}}</h3>
                <h5>{{character.category}}</h5>
                <h6>{{character.status}}</h6>
            </div>
        </div>
  </div>
</template>



<style lang="scss" scoped>
@import './styles/partials/variables'; 

.ft-card{
    background-color: $primary-color;
    .ft-single-card{
        margin: 10px;
        text-align: center;
        padding: 10px 0px;
        .img{
        height: 250px;
            img{
            object-fit: cover;
            object-position: top;
            max-width: 100%;
            overflow: hidden;
            }
        }
    }
    .card-text{
        h3{
            text-transform: uppercase;
            font-size: 18px;
        }
        h5{
            text-transform: capitalize;
            color: rgb(138, 136, 136);
        }
        h6{
            text-transform: capitalize;
            color: rgb(138, 136, 136);
        }
    }
}

.col-3{
    width: 20%;
}

</style>