<template lang="html">
  <div class="">
    <img :src="spaceImageUrl" alt="random space image">
    <button @click="handleClick">Like</button>
  </div>
</template>

<script>
import {eventBus} from '../main.js';
export default {
  props: ["spaceImageUrl"],
  methods: {
    handleClick(){
      eventBus.$emit("selected-image", this.imageUrl)
    }
  }
}
</script>

<style lang="css" scoped>
  img{
    width: 500px;
    height: 500px;
  }
</style>
