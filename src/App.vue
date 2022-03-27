<template>
  <div id="app">
    <div class="page-header">
      <h1>readme sin tacokalkulator</h1>
    </div>
    <p
      class="lead center"
    >For nye medlemmer, gamle drankere og andre som ønsker å kokkelere readmes fantastiske taco, men som er usikker på hvor mye de trenger av alt mulig.</p>
    <TacoCalc />

    <div id="footer">
      <p>
        Made by
        <a href="http://svorstol.com">Stein-Otto Svorstøl</a>
      </p>
      <p>
        Maintained by
        <a href="https://github.com/orgs/readme-ntnu/">readme</a>
      </p>
    </div>
  </div>
</template>

<script>
import TacoCalc from './components/TacoCalc.vue'


export default {
  name: 'app',
  components: {
    TacoCalc
  }
}
</script>

<style>
  #app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }

  #footer {
    text-align: center;
    font-size: 10px;
    color: grey;
    position: relative;
    bottom: -50px;
  }

  .aligncenter {
    float: center;
    text-align: center;
  }

  .alignright {
    float: right;
  }
</style>
