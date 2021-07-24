<template>
  <div id="app">
    <Navbar/>
    <div class="spotify-artist" id="spotify-artist">
      <iframe src="https://open.spotify.com/embed/artist/1rrksm4Ji3AAyzlUqLmxup?theme=0" width="100%" height="380" frameBorder="0" allowtransparency="true" allow="encrypted-media"></iframe>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator"
import Navbar from "./components/Navbar.vue"

@Component({
  components: {
    Navbar
  }
})
export default class App extends Vue {}
</script>

<style>
  @font-face {
  font-family: "Helvetica";
  src: local("Helvetica"),
    url(./fonts/Helvetica/Helvetica.ttf) format("truetype");
  }
  html {
    margin: 0;
    font-family: Helvetica;
    height: 100%;
    overflow: hidden;
  }
  body{
    margin: 0;
    height: 100%;
  }
  #app {
    height: 100%;
    width: 100%;
    margin: 0;
    background: url('./assets/background.jpg') no-repeat center center !important;
    background-size: cover !important;
  }
  .spotify-artist{
    width: 50%;
    margin: auto;
  }

  .spotify-artist iframe{
    width: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: auto !important;
  }
</style>
