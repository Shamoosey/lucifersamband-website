<template>
  <div id="app">
    <Navbar/>
    <router-view/>
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
    background-color: #FAFAFF;
    margin: 0;
    font-family: Helvetica;
  }
  body{
    margin: 0;
  }
  #app{
    margin: 0;
  }
</style>
