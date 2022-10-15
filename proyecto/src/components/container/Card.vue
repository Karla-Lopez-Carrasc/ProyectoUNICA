<script setup>
import Message from '../base/Message/Message.vue';
import Secondary from '../base/Button/Secondary.vue';
import Image from '../../assets/images/poster1.jpeg'

defineProps({
    url: {
        type: String,
        default: Image
    },
    category: {
        type: String,
        default: 'action'
    },
    title: String,
    disabled: Boolean
})
</script>

<template>
    <div :class="category" class="card">
        <img class="card__img" :src="url" alt="poster película">
        <Message :category="category" :title="title"/>
        <Secondary :disabled="disabled" class="card__secondary" :state="category" :text="'Ver lista'"/>
    </div>
</template>

<style>
.card{
    min-width: 200px;
    width: 100%;
    height: 350px;
    padding: 15px;
    margin: 15px;
    border-style: solid;
    border-width: 2px;
    border-radius: 0.8rem;
}
.card:hover{
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
.card__img{
    width: 100%;
    height: 175px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.274), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    border-radius: 0.5rem;
}

.card__secondary{
    height: 30px;
}

.action{
    border-color: rgba(128, 128, 128, 0.644);
    border-color: rgba(240, 188, 151, 0.774);
    background-color: rgba(128, 128, 128, 0.158);
    background-color: rgba(255, 228, 196, 0.548);
}/*
.comedy {
    border-color: #eab308;
    background-color: #fef08a;
}
.horror {
    border-color: #ef4444;
    background-color: #fecaca;
}*/
</style>