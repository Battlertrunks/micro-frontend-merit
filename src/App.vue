<template>
  <div class="container" id="app">
    <div class="content">
      <img alt="Vue logo" src="./assets/logo.png">
      <h1>This is a Vue SPA page</h1>
      <h2>Random Number: {{ randomNum }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      randomNum: 0,
      dispatcher: new Event('start')
    }
  },
  created() {
    const uri = window.location.search.substring(1);
    const params = new URLSearchParams(uri);
    console.log(params.get('randomNum'));
    this.randomNum = params.get('randomNum');
  }

}
</script>

<style lang="scss">
  $backgroundColor: #242424;

  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    .content {
      text-align: center;
    }

    h1 {
      color: #eee;
      font-size: 2.5rem;
    }
    h2 {
      color: #eee;
      font-size: 1.5rem;
    }
  }



body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: $backgroundColor;
}
</style>
