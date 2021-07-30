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
      <div class="spotify-album" ref="spotify">
          <div v-for="(item, i) in spotifyAlbum" :key="i" class="spotify-album-wrapper">
            <a :href="item.url" :target="'_blank'" class="spotify-album-a">
              <span class="spotify-album-text">{{item.meta}}</span>
              <v-img :src="item.img" :alt="item.meta" class="spotify-album-img"/>
            </a>
          </div>
      </div>
      <div class="spotify-artist panel" id="spotify">
        <iframe src="https://open.spotify.com/follow/1/?uri=spotify:artist:1rrksm4Ji3AAyzlUqLmxup?si=oW4wHioCSwuOnyI0OyI9Uw&dl_branch=1&size=detail&theme=dark&show-count=0" width="300" height="56" scrolling="no" frameborder="0" style="border:none; overflow:hidden;" allowtransparency="true"></iframe>
        <br/>
        <iframe src="https://open.spotify.com/embed/artist/1rrksm4Ji3AAyzlUqLmxup?theme=0" width="100%" height="380" frameBorder="0" allowtransparency="true" allow="encrypted-media"></iframe>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator"
import Navbar from "./components/Navbar.vue"
import { Interfaces } from "./interfaces"
let desolation = require("./static/desolation.jpg")
let authority = require("./static/authority.jpg")

@Component({
  components: {
    Navbar
  }
})
export default class App extends Vue {
  getImagePath() {
    return desolation
  }

  spotifyAlbum: Interfaces.SpotifyAblum[] = [
    {
      img: authority,
      url: "https://open.spotify.com/album/1gFynAvkvrTQaPYOrRudoq?si=l879El75S0y8SoX0doXwlw&dl_branch=1",
      meta: "authority"
      
    },
    {
      img:desolation,
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
    height: 50%;
  }
  .spotify-artist{
    margin: auto;
    height: auto;
    width: 40%;
  }
  .spotify-artist iframe{
    display: flex;
    align-items: center;
    justify-content: center;
    margin: auto !important;
    width: 100%;
  }
  .spotify-album {
    width: 100%;
    display: flex;
    justify-content: center;
    flex-direction: row;
  }
  a {
    text-decoration: none;
    color:white;
  }
  a :hover {
    text-decoration: none;
    color:white;
  }
  a :visited {
    text-decoration: none;
    color:white;
  }
  .spotify-album-wrapper {
    margin: auto;
    width: 375px
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

  @media screen and  (max-width: 880px) {
    .app-subcontent {
      height: auto;
    }
    .spotify-album {
      flex-direction: column;
      height: auto;
      margin-bottom: 20px;
    }
    .spotify-album-wrapper {
      padding: 20px 0px;
    }
    .spotify-artist{
      margin: auto;
      height: auto;
      width: 75%;
    }
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
