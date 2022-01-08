<template>
  <h3>{{ msg }}</h3>
</template>

<script>
export default {
    name: 'Cuerpo',
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