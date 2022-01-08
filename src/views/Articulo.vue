<template>
    <div v-if="error">
        <p>Error: {{ error }}</p>
    </div>
    <div v-else>
        <Titulo :msg="article.title"/>
        <Cuerpo :msg="article.body" />
    </div>
  
  
</template>

<script>
import Titulo from '../components/Titulo.vue';
import Cuerpo from '../components/Cuerpo';

export default {
    components : {
        Titulo, Cuerpo
    },
    data () {
        return {
            article: {},
            error: null
        }
        
    },
    methods: {
        async getArticle() {
            try {
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`);
                this.article  = await data.json();
                console.log(data);
            } catch (error) {
                console.log('hooañ')
                this.error = error;
                console.log(error);
            }
        }
    },
    /*
    beforeMount() {
        this.consumirApi();
    }*/
    created() {
        this.getArticle();
    }
}
</script>

<style>

</style>