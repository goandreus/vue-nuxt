<template>
    <div class="container">
        <div class="row">
            <div class="col-md-3" v-for="(item, index) in articulos" :key="index">
                <h2>
                    <nuxt-link :to="`/blog/${item.id}`">{{item.titulo}}</nuxt-link>
                </h2>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            articulos:[
                {id: 1,titulo: 'Titulo #1'},
                {id: 2,titulo: 'Titulo #2'},
                {id: 3,titulo: 'Titulo #3'},
                {id: 4,titulo: 'Titulo #4'},

            ]
        }
    }
}
</script>

