<template>
  <div class="container">
    <div class="header-outline">
      <img class="logo" src="~/assets/logo.svg" />
      <div class="score-display">
        <h4 class="score-text">SCORE</h4>
        <h1 class="score">{{ score }}</h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      score: 0,
    }
  }
}
</script>

<style scoped>
.container {
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid orange;
}
.header-outline {
  width: 80%;
  max-width: 600px;
  margin: 50px 0 20px 0;
  border: 3px solid hsl(217, 16%, 45%);
  border-radius: 20px;

  align-self: center;
  justify-self: center;

  padding: 15px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.score-display {
  width: 150px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: white;
  border-radius: 15px;
}

.score-text {
  color: hsl(229, 64%, 46%);
}

.score {
  font-size: 400%;
  color: hsl(229, 25%, 31%);
}
</style>>
