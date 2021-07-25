<template>
  <div id="app">
    <div class="app-main">
      <Navbar/>
      <div class="app-main-title">
        <h1>
          Lucifer Sam and the <br/>
          Psychedelic Band
          </h1>
      </div>
    </div>
    <div class="app-subcontent" id="app-subcontent">
      <div class="spotify-artist panel" id="spotify" ref="spotify">
        <iframe src="https://open.spotify.com/embed/artist/1rrksm4Ji3AAyzlUqLmxup?theme=0" width="100%" height="380" frameBorder="0" allowtransparency="true" allow="encrypted-media"></iframe>
      </div>
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
export default class App extends Vue {
  getImagePath(image:string) {
    return require(`./assets/img/${image}`);
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:ital,wght@1,700&display=swap');
  @font-face {
  font-family: "Helvetica";
  src: local("Helvetica"),
    url(./fonts/Helvetica/Helvetica.ttf) format("truetype");
  }
  html {
    margin: 0;
    font-family: Helvetica;
    height: 100%;
    /* hides scrollbar overflow: hidden; */
  }
  body{
    margin: 0;
    height: 100%;
  }
  #app {
    height: 100%;
    width: 100%;
    margin: 0;
    background: url('./assets/img/background.jpg') no-repeat center center !important;
    background-size: cover !important;
    background-attachment: fixed !important;
    background-position: center !important;
    background-repeat: no-repeat !important;
  }
  .app-main{
    height: 100%;
  }
  .spotify-artist{
    margin: auto;
    width:30%;
    height: 5%;
  }
  .spotify-artist iframe{
    display: flex;
    align-items: center;
    justify-content: center;
    margin: auto !important;
  }
  .app-subcontent {
    height: 100%;
  }
  .app-main-title{
    font-family: 'Josefin Sans', sans-serif;
    color: white;
    text-align: center;
    font-size: 34px;
  }
</style>
