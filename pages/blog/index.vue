<template>
    <div class="container mt-5">
        <div class="card my-2" v-for="(item, index) in articulos" :key="index">
            <nuxt-link :to="`blog/${item.id}`">
                <h1>{{item.title}}</h1>
            </nuxt-link>
            <p>{{item.body}}</p>
            <div class="card-body">
                <h1>Titulo</h1>
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium corporis neque eveniet laborum aliquid earum fugiat aperiam, nihil, quam provident, quisquam adipisci. Dicta, ut quod ipsum autem quisquam quas pariatur.
                </p>
            </div>
        </div>
    </div>
</template>

<script>

import axios from 'axios';

export default {
    data(){
        return{
            articulos:[
               

            ]
        }
    },
    
    
    async created(){

        try{
        const res = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
        console.log(res.data);
        this.articulos = res.data
        }catch(error){
            console.log(error)
        }
    }
}
</script>

