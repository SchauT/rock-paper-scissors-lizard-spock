<template>
  <div class="__nuxt-landing-page">
    <Game class="game-container" />
    <div class="rules-button" @click="showHelp">
      RULES
    </div>
    <HelpPopup class="help-popup" v-show="isHelpVisible" @closeHelp="closeHelp"/>
  </div>
</template>

<script>
import Vue from 'vue'
import Game from '~/components/Game.vue'
import HelpPopup from '~/components/HelpPopup.vue';

export default Vue.extend({
  name: 'RPSLSgame',
  components: {
    Game,
    HelpPopup
  },
  head () {
    return {
      title: 'Rock Paper Scissors Lizard Spock Game',
      meta: [
        {
          hid: 'rock paper scissors lizard spock game',
          name: 'rock paper scissors lizard spock game',
          content:
            "The best Rock Paper Scissors Lizard Spock game you'll see in your life !"
        }
      ]
    }
  },
  data() {
    return {
      isHelpVisible: false
    };
  },
  methods: {
    showHelp() {
      this.isHelpVisible = true;
    },
    closeHelp() {
      this.isHelpVisible = false;
    }
  }
})
</script>

<style scoped>
.game-container {
  height: 60vh;
}
.rules-button {
  position: absolute;
  bottom: 20px;
  right: 20px;

  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid white;
  border-radius: 5px;
  text-transform: uppercase;
  cursor: pointer;
  transition: all 0.2s;
  color: white;
  font-weight: 500;
  text-decoration: none;
  font-size: x-large;
  flex: 1 auto;
}
.rules-button:hover {
  color: hsl(237, 49%, 15%);
  background-color: white;
}

@media only screen and (max-width: 576px) {
  .rules-button {
    right: 50%;
    transform: translateX(50%);
  }
}
</style>
