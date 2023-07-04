<script>
import axios from 'axios';
export default{
    created(){
    this.getPokemon();
  },
  props:{
    store:Object
  },
    methods:{
      getPokemon(){
        axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons')
        .then((res)=>{
          res.data.docs.forEach(doc => {
          this.store.pokemons.push(doc)
          });
        })
      }
    }
}
</script>


<template>
    <main class="row">
        <div v-for="pokemon in store.pokemons" class="card col">
            <img :src="pokemon.imageUrl" alt="">
            <div>
                <p>{{ pokemon.number }}</p>
                <p>{{pokemon.name}}</p>
                <p>{{ pokemon.type1 }}</p>
            </div>
        </div>
    </main>

</template>



<style>
.card{
    height: 100px;
    width: 100px;
}
</style>