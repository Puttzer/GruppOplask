<template>
  <div class="gallery">
    <div class="wrapper" v-for="image in images" v-bind:key="image.id">
      <img :src="image.url" alt />
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      images: [
        {
          url: "",
          id: 
        }
      ]
    };
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