
<script setup>

import FiboCard from "./components/FiboCard.vue";

import { ref, reactive } from "vue";

const cardValues = ref([1, 2, 3, 5, 8, 13, 21, 34]);

const playedCards = ref([]);

function addCard(card) {

  playedCards.append(card)
  console.log(playedCards)
}

</script>

<template>
  <div class="container">
    <div class="centro-cartas" >
      <FiboCard v-for="card in playedCards" v-bind:valor="card"/>
    </div>

    <div class="maso-cartas" @cardPlayed="addCard(card)">

      <FiboCard v-for="card in cardValues" v-bind:valor="card" v-bind:card-in-deck="true" />
    </div>

    <div></div>
  </div>
</template>

<style scoped>
.container {
  flex-direction: column;
  flex-grow: 1;
  width: 100%;
  height: 100%;
}

.centro-cartas {
  width: 100%;
  background-color: beige;
  height: 70%;
  display: flex;
  justify-content: space-around;
}

.maso-cartas {
  display: flex;
  width: 100%;
  height: 30%;
  background-color: cadetblue;
  justify-content: space-around;
  align-items: center;
}
</style>
