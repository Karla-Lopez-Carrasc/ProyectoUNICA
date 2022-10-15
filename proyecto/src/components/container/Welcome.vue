<script setup class="texto">
defineProps({
    text: {
        type: String,
        default: 'Aquí encontrarás una lista de restaurantes de acuerdo a lo que busques'
    }
})
</script>

<template>
    <div class="w-full h-64 grid justify-items-center pt-6">
        <img class="w-1/2 mt-10" src="https://museosalinasdelcarmen.es/wp-content/uploads/2019/07/restaurante.png" alt="imagen">
        <p class="text-base font-semibold">{{text}}</p>
    </div>
</template>

<style>
    .texto{
        margin: auto;
    }

</style>