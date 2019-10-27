<template>
  <div class="">
    <space-image-component :spaceImageUrl="spaceImageUrl"></space-image-component>
  </div>
</template>

<script>
import SpaceImageComponent from './components/SpaceImageComponent.vue'
import {eventBus} from "./main.js"
export default {
  name: 'app',
  data() {
    return {
      spaceImageUrl: "",
      favouriteImages: []
    }
  },
  mounted() {
    fetch("https://api.nasa.gov/planetary/apod?api_key=NNyHUQ6sEV3leyDXe1uLwrBXIDmBMlnpjcz9fMtq")
    .then(response => response.json())
    .then(spaceImageData => this.spaceImageUrl = spaceImageData.url)

    eventBus.$on("selected-image", (selectedSpaceUrl) => {
      this.favouriteImages.push(selectedSpaceUrl);
    })
  },
  components: {
    "space-image-component": SpaceImageComponent
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
