<script>
import AppMain from'./components/AppMain.vue';
import {store} from './assets/data/store.js';
import SearchForm from './components/SearchForm.vue';
export default{
  components:{ AppMain,SearchForm },
  data(){
      return{
        store,
        selectionType:''
      }
    },
  methods:{
    oneTermChange(term){
      this.selectionType=term;
    }
  }
}
</script>


<template>
  <SearchForm @term-change="onTermChange"/>
 <AppMain :store="store"/>
</template>

<style>
body{
  background-image: url(./assets/img/5818392.jpg);
  background-repeat: no-repeat;
  height: 100vh;
}
</style>