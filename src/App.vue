<script>
import AppMain from'./components/AppMain.vue';
const endpoint='https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import {store} from './assets/data/store.js';
import SearchForm from './components/SearchForm.vue';
import axios from 'axios';
export default{
  components:{ AppMain,SearchForm },
  data(){
      return{
        store,
      }
    },
  methods:{
    oneChange(term){
      const selectType=`https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=${term}`;
      axios.get(selectType).then((res)=>{
        this.store.pokemons=res.data.docs
      })
    },
  }
}
</script>


<template>
  <SearchForm @form-submit="oneChange"/>
 <AppMain :store="store"/>
</template>

<style>
body{
  background-image: url(./assets/img/5818392.jpg);
  background-repeat: no-repeat;
  height: 100vh;
}
</style>