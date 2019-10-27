<template lang="html">
<div class="favouritelistitem">
  <image :spaceImageUrl="image"></image>
</div>
</template>

<script>
import {eventBus} from "./main.js";
import SpaceImageComponent from "./components/SpaceImageComponent";

export default {
  name: 'favourite-list-item',
  props: ["image"],
  components: {
    "favourite-list": FavouriteList

  }
}

};
</script>

<style lang="css" scoped>
</style>
