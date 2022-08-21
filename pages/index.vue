<template>
  <div class="__nuxt-landing-page">
    <h1>This is game</h1>
    <div class="rules-button">RULES</div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'RPSLS Game'
})
</script>

<style scoped>
.__nuxt-landing-page {
  width: 100vw;
  flex-grow: 1;

  border: 1px solid red;
}
.rules-button {
  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid white;
  border-radius: 5px;
  text-transform: uppercase;
  cursor: pointer;
  transition: all .2s;
  color:white;
  font-weight: 500;
  text-decoration: none;
  font-size: x-large;
  flex: 1 auto;
  justify-content: space-around;
}
.rules-button:hover {
  color: hsl(237, 49%, 15%);
  background-color: white;
}
</style>