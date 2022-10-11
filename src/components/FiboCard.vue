
<template>

    <div v-if="state.cardInDeck != false" class="card" @click="playCard" >
        <p>{{props.valor}}</p>
    </div>


</template>

<script setup>

import { reactive } from 'vue';

const state = reactive({cardInDeck: true});
const emit = defineEmits(['cardPlayed'])

function playCard() {
    state.cardInDeck = !state.cardInDeck;
    emit('cardPlayed', valor);
    console.log(state.cardInDeck);
}
 
    const props = defineProps({
        valor: Number,
        cardInDeck: Boolean,
    })

    

</script>

<style>

    .card {
        padding: 12px 24px;
        background-color: brown;
        width: 50px;
        height: fit-content;
        border-radius: 10px;
    }

    div > p {
        color: white;
        font-size: 36px;
    }

</style>