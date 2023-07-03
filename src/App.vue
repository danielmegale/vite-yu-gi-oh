<script>
import AppMain from'./components/AppMain.vue';
import {store} from './assets/data/store.js' 
export default{
  components:{ AppMain },
  data(){
      return{
        store
      }
    },
}
</script>


<template>
 <AppMain :store="store"/>
</template>

<style>
body{
  background-image: url(./assets/img/5818392.jpg);
  background-repeat: no-repeat;
  height: 100vh;
}
</style>