<template>
  <div class="game">
    <div class="step1-container">
      <img class="bg-pentagon" src="~/assets/bg-pentagon.svg">
      <GameButton
        class="game-button scissors-button"
        type="scissors"
        color-a="hsl(40, 84%, 53%)"
        color-b="hsl(39, 89%, 49%)"
        @onClick="play"
      />
      <GameButton
        class="game-button paper-button"
        type="paper"
        color-a="hsl(230, 89%, 65%)"
        color-b="hsl(230, 89%, 62%)"
        @onClick="play"
      />
      <GameButton
        class="game-button rock-button"
        type="rock"
        color-a="hsl(349, 70%, 56%)"
        color-b="hsl(349, 71%, 52%)"
        @onClick="play"
      />
      <GameButton
        class="game-button lizard-button"
        type="lizard"
        color-a="hsl(261, 72%, 63%)"
        color-b="hsl(261, 73%, 60%)"
        @onClick="play"
      />
      <GameButton
        class="game-button spock-button"
        type="spock"
        color-a="hsl(189, 58%, 57%)"
        color-b="hsl(189, 59%, 53%)"
        @onClick="play"
      />
    </div>
  </div>
</template>

<script lang="ts">
import GameButton from './GameButton.vue'

type playType = 'scissors' | 'paper' | 'rock' | 'lizard' | 'spock';
type players = 'player' | 'computer' | 'draw';

function sleep (ms: number) {
  return new Promise(resolve => setTimeout(resolve, ms))
}
async function getRandomPlay () {
  await sleep(2000)
  const randInt: number = Math.floor(Math.random() * 5)
  switch (randInt) {
    case 0:
      return 'scissors'
    case 1:
      return 'paper'
    case 2:
      return 'rock'
    case 3:
      return 'lizard'
    default:
      return 'spock'
  }
}

export default {
  components: { GameButton },
  methods: {
    async play (played: playType) {
      const computed: playType = await getRandomPlay()

      let winner: players = 'player'
      switch (played) {
        case 'scissors':
          if (computed === 'rock' || computed === 'spock') {
            winner = 'computer'
          }
          if (computed === 'scissors') {
            winner = 'draw'
          }
          break

        case 'paper':
          if (computed === 'scissors' || computed === 'lizard') {
            winner = 'computer'
          }
          if (computed === 'paper') {
            winner = 'draw'
          }
          break

        case 'rock':
          if (computed === 'paper' || computed === 'spock') {
            winner = 'computer'
          }
          if (computed === 'rock') {
            winner = 'draw'
          }
          break

        case 'lizard':
          if (computed === 'rock' || computed === 'scissors') {
            winner = 'computer'
          }
          if (computed === 'lizard') {
            winner = 'draw'
          }
          break

        default:
          if (computed === 'lizard' || computed === 'paper') {
            winner = 'computer'
          }
          if (computed === 'spock') {
            winner = 'draw'
          }
          break
      }

      $nuxt.$emit('emitWinner', winner)
    }
  }
}
</script>

<style scoped>
.game {
  display: flex;
  justify-content: center;
  align-items: center;

  border: 0.5px solid white;
}
.step1-container {
  position: relative;
}
.game-button {
  position: absolute;
  width: 130px;
  height: 130px;
}
.scissors-button {
  top: -15%;
  right: 50%;
  transform: translateX(50%);
}
.paper-button {
  right: -15%;
  bottom: 45%;
}
.rock-button {
  bottom: -15%;
  right: 5%;
}
.lizard-button {
  bottom: -15%;
  left: 5%;
}
.spock-button {
  left: -15%;
  bottom: 45%;
}

@media only screen and (max-width: 576px) {
  .bg-pentagon {
    width: 90%;
    height: 90%;
  }
  .game-button {
    width: 110px;
    height: 110px;
  }
}
</style>
