<template>
  <div class="game">
    <div class="step1-container">
      <img class="bg-pentagon" src="~/assets/bg-pentagon.svg">
      <GameButton class="game-button scissors-button" type="scissors" color-a="hsl(40, 84%, 53%)" color-b="hsl(39, 89%, 49%)" />
      <GameButton class="game-button paper-button" type="paper" color-a="hsl(230, 89%, 65%)" color-b="hsl(230, 89%, 62%)" />
      <GameButton class="game-button rock-button" type="rock" color-a="hsl(349, 70%, 56%)" color-b="hsl(349, 71%, 52%)" />
      <GameButton class="game-button lizard-button" type="lizard" color-a="hsl(261, 72%, 63%)" color-b="hsl(261, 73%, 60%)" />
      <GameButton class="game-button spock-button" type="spock" color-a="hsl(189, 58%, 57%)" color-b="hsl(189, 59%, 53%)" />
    </div>
  </div>
</template>

<script>
import GameButton from './GameButton.vue'
export default {
  components: { GameButton }
}
</script>

<style scoped>
.game {
  display: flex;
  justify-content: center;
  align-items: center;

  border: 0.5px solid white;
}
.bg-pentagon {
  border: 2px solid purple;
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
