<template>
  <div>
      <Header />
      <Nuxt />
  </div>
</template>

<script>
import Header from '~/components/Header.vue';

export default {
	components: {
        Header
}}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  color: white;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

body, html {
  width: 100%;
  height: 100%;
  margin: 0px;
}

body {
  background: radial-gradient(ellipse at top, hsl(214, 47%, 23%), hsl(237, 49%, 15%));
  display: flex;
  flex-direction: column;
  align-items: center;
  align-content: center;
}
</style>