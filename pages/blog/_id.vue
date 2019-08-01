<template>
    <div class="container">
        <div class="card">
            <div class="card-body">
                <h1>{{articulos.title}}</h1>
                <p class="small">{{articulos.nombreAutor}}</p>
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
            
        }
    },
    //async created(){
    //    try{
    //    const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
    //    this.articulos = res.data;

    //    const resAutor = await axios.get(`https://jsonplaceholder.typicode.com/users/${res.data.userId}`)
    //    this.articulos.nombreAutor = resAutor.data.name;
    //    }catch(error){
    //        console.log(erorr);
    //    }
    //},

    async asyncData({isDev, route, store, env, params, query, req, res, redirect, error}) {
        try{
        const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`)
        const articulos = res.data;

        const resAutor = await axios.get(`https://jsonplaceholder.typicode.com/users/${res.data.userId}`)
        articulos.nombreAutor = resAutor.data.name;

        return {articulos};
        }catch(error){
            console.log(erorr);
            return {error:error}
        }
    },
}
</script>
