<template>
  <div class="game-button" :style="cssProps" @click="onClick">
    <div class="white-center">
      <img class="image" :src="require(`~/assets/icon-${type.toLowerCase()}.svg`)">
    </div>
  </div>
</template>

<script>
export default {
  props: {
    id: '',
    type: {
      type: String,
      default: 'rock'
    },
    colorA: {
      type: String,
      default: 'black'
    },
    colorB: {
      type: String,
      default: 'white'
    }
  },
  computed: {
    cssProps () {
      return {
        '--contour-color-a': this.colorA,
        '--contour-color-b': this.colorB,
        '--contour-shadow': this.darkenHsl(this.colorB)
      }
    }
  },
  methods: {
    onClick () {
      this.$emit('onClick', this.type)
    },
    darkenHsl (color) {
      if (color.charAt(0) !== 'h') {
        return
      }
      const splited = color.split('%')
      let lightness = splited[splited.length - 2].substring(1)
      lightness = parseInt(lightness) - 15
      splited[splited.length - 2] = ', ' + lightness

      return splited.join('%')
    }
  }
}
</script>

<style scoped>
.game-button, .white-center {
    border-radius: 50%;

    display: flex;
    justify-content: center;
    align-items: center;
}
.game-button {
    width: 100%;
    height: 100%;
    background: linear-gradient(var(--contour-color-a), var(--contour-color-b));
    box-shadow: 0px 6px var(--contour-shadow);
}
.game-button:hover {
    box-shadow: 0px 0px transparent;
    translate: 0px 5px;
}
.white-center {
    width: 75%;
    height: 75%;
    background-color: white;
    box-shadow: inset 0px 5px lightgray;
}

@media only screen and (max-width: 576px) {
    .image {
        width: 55%;
        height: 55%;
    }
}
</style>
