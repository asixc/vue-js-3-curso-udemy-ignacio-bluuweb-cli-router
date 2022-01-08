<template>
  <h1>{{ msg }}</h1>
</template>

<script>
export default {
    name: 'Titulo',
    props:{
        msg:{
            type: String, 
            value: ''
        }
    } 
    
}
</script>

<style>

</style>