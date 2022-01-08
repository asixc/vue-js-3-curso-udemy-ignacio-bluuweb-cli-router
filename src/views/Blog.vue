<template>
  <Titulo msg="Título de mi blog" />
  <!-- <button @click="consumirApi">Get posts</button> -->
  <hr>
  <div v-for="(item, index) in arrayBlogs" :key="index"> 
      <span><router-link :to="`/blog/${item.id}`">id: {{ item.id }} - {{ item.title}} </router-link></span>
  </div>
</template>

<script>
import Titulo from '../components/Titulo';

export default {
    components: {
        Titulo
    },
    data () {
        return {
            arrayBlogs: []
        }
        
    },
    methods: {
        async consumirApi() {
            try {
                const data = await fetch('https://jsonplaceholder.typicode.com/posts');
                const arrayBlogs = await data.json();
                this.arrayBlogs = arrayBlogs;
               // console.log(array);
            }catch (error) {
                console.log(error);
            }
        }
    },
    /*
    beforeMount() {
        this.consumirApi();
    }*/
    created() {
        this.consumirApi();
    }

}
</script>

<style>

</style>