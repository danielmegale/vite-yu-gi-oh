<script>
import axios from 'axios';
import {store} from '../assets/data/store.js';

export default{
    data(){
        return{
            searchTerm:'',
            store,
        }
    },
    emits:['term-change','form-submit'],
    methods:{
        submitForm(){
            this.$emit('form-submit',this.searchTerm)
        },
        resetForm(){
            this.searchTerm='';
            this.submitForm();
        },
    }
};
</script>


<template>
    <form action="">
        <select v-model="searchTerm" @change="$emit('form-submit',searchTerm)">
            <option v-for="typology in store.types">{{typology}}</option>
        </select>
    </form>
</template>


<style>

</style>