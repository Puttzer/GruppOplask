<template>
  <div class="gallery">
    <Lightbox :show="show" @close="show=false" :bigImage="bigImage" />
    <div class="wrapper" v-for="image in images" v-bind:key="image.id">
      <img :src="image.urls.small" alt v-on:click="showLightbox(image.urls.full)" />
    </div>
  </div>
</template>

<script>
import Lightbox from "./Lightbox";
export default {
  components: { Lightbox },
  props: {
    images: Array
  },
  data: () => {
    return {
      show: false,
      bigImage: ""
    };
  },

  methods: {
    showLightbox(bigURL) {
      this.show = true;
      this.bigImage = bigURL
    }
  }
};
</script>

<style lang="scss" scoped>
.gallery {
  display: grid;
  grid-gap: 10px;
  grid-template-columns: repeat(3, 1fr);

  .wrapper {
    img {
      max-width: 310px;
    }
  }
}
</style>