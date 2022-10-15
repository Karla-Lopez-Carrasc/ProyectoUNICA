<script setup>
import axios from 'axios'
import Movies from './data.js'
import Card from '../Card.vue'
import { onMounted } from 'vue'

let userState = false
let moviesInfo = null
const userInfo = JSON.parse(localStorage.getItem('user-info'))


onMounted(() => {
   infoMovies()
})

async function infoMovies(){
    let moviesAxios = await axios.get('http://localhost:3000/movies').then(data => moviesInfo = data.data)
    console.log(moviesAxios)
}

try{
    if(userInfo.name && userInfo.email){
        userState = true
    }
}
catch{
    userState = false
}

</script>

<template>
    <div class="movies pt-12">
        <div class="movies__card" v-for="Movie in Movies" :key="Movie.id">
            <Card   
            :title="Movie.title"
            :category="Movie.category"
            :url="Movie.url"
            :disabled="!userState"
            ></Card>
        </div>
    </div>
</template>

<style>
.movies {
    bottom: 10px;
    width: 100%;
    min-height: 100vh;
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-gap: 10px;
    padding-bottom: 100px;
}
.movies__card {
    display: flex;
    justify-content: center;
}

@media screen and (max-width: 1200px) {
    .movies {
        grid-template-columns: repeat(4, 1fr);
    }
}

@media screen and (max-width: 900px) {
    .movies {
        grid-template-columns: repeat(3, 1fr);
    }
}

@media screen and (max-width: 690px) {
    .movies {
        grid-template-columns: repeat(2, 1fr);
    }
}
@media screen and (max-width: 475px) {
    .movies {
        grid-template-columns: repeat(1, 1fr);
        min-width: 325px;
    }
}
</style>