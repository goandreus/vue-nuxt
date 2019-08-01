<template>
    <div class="container">
        <div class="card">
            <div class="card-body">
                <h1>{{articulos.title}}</h1>
                <p class="small">{{articulos.userId}}</p>
                <p>{{articulos.body}}</p>
                <nuxt-link to="/blog" class="btn btn-primary">Atras</nuxt-link>
            </div>
        </div>
    </div>
</template>

<script>

import axios from 'axios';
export default {

    data(){
        return {
            articulos: ''
        }
    },
    async created(){
        try{
        const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)

        this.articulos = res.data;
        }catch(error){
            console.log(erorr);
        }
    }
}
</script>
