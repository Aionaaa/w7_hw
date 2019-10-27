<template lang="html">
<div id="favourites-list">
  <h1>Your Liked Images</h1>
  <ul>
    <favourite-list-item v-for="(image, index) in favourites"
    :image="image"
    :key="index"
    ></favourite-list-item>
  </ul>
</div>
</template>

<script>
import FavouriteListItem from "./components/FavouriteListItem";
import SpaceImageComponent from "./components/SpaceImageComponent";
export default {
  props: ["selected-image"],
  components: {
    "favourite-list-item": FavouriteListItem,
    "space-image-component": SpaceImageComponent
  }
};
</script>

<style lang="css" scoped>
</style>
