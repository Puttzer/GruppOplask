<template>
  <div class="gallery">
    <div class="wrapper" v-for="image in images" v-bind:key="image.id">
      <img :src="image.url" alt @click="test()" />
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      images: [
        {
          url:
            "https://images.unsplash.com/photo-1461988320302-91bde64fc8e4?ixid=2yJhcHBfaWQiOjEyMDd9&&fm=jpg&w=400&fit=max",
          id: 1
        }
      ]
    };
  },

  methods: {
    test: function test() {
      console.log("yes");
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