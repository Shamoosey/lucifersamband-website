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
      <div class="spotify-album">
        <v-row no-gutters>
          <v-col v-for="(item, i) in spotifyAlbum" :key="i" :class="n === 1 ? 'mb-6' : ''">
            <!-- <v-img :src="require(`./assets/img/${item.img}`)">
            </v-img> -->
          </v-col>  
        </v-row>
      </div>
      <div class="spotify-artist panel" id="spotify" ref="spotify">
        <iframe src="https://open.spotify.com/embed/artist/1rrksm4Ji3AAyzlUqLmxup?theme=0" width="100%" height="380" frameBorder="0" allowtransparency="true" allow="encrypted-media"></iframe>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator"
import Navbar from "./components/Navbar.vue"
import { Interfaces } from "./interfaces"

@Component({
  components: {
    Navbar
  }
})
export default class App extends Vue {
  getImagePath(image:string) {
    return require(`./assets/img/${image}`);
  }

  spotifyAlbum: Interfaces.SpotifyAblum[] = [
    {
      img:"authority",
      url: "https://open.spotify.com/album/1gFynAvkvrTQaPYOrRudoq?si=l879El75S0y8SoX0doXwlw&dl_branch=1",
      meta: "authority"
    },
    {
      img:"desolation",
      url: "https://open.spotify.com/album/1RMJ15NSVcUeBpft9mWbmg?si=syT0yPPKR1GrKhTy5-hLbg&dl_branch=1",
      meta: "desolation"
    }
  ]
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
  .spotify-album{
    width: 100%;
    height: 60%;
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
    background-color: #1E1E1E;
  }
  .app-main-title{
    font-family: 'Josefin Sans', sans-serif;
    color: white;
    text-align: center;
    font-size: 34px;
  }

  ::-webkit-scrollbar {
    width: 10px;
    background: #1E1E1E;
  }

  ::-webkit-scrollbar-track {
    background-color: transparent !important;
    width: 10px;
  }

  ::-webkit-scrollbar-thumb {
    background: #888;
    border-radius: 15px;
  }

  ::-webkit-scrollbar-thumb:hover {
    background: #555;
  }
</style>
