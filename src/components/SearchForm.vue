<script>
export default{
    data(){
        return{
            searchTerm:'',
        }
    },
    emits:['term-change']
};
</script>


<template>
    <form action="">
        <input type="text" id="" v-model.trim="searchTerm" @keyup="$emit('term-change',searchTerm)">
    </form>
</template>


<style>

</style>