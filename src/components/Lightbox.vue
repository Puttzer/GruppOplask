<template>
  <div class="lightbox" v-if="show == true" @click="closething()">
    <div class="wrapper" v-for="image in images" v-bind:key="image.id">
      <img :src="image.url" alt />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    show: Boolean
  },
  data() {
    return {
      images: [
        {
          url:
            "https://images.unsplash.com/photo-1461988320302-91bde64fc8e4?ixid=2yJhcHBfaWQiOjEyMDd9&fm=jpg&fit=crop&w=1080&q=80&fit=max",
          id: 1
        }
      ]
    };
  },

  methods: {
    closething: function() {
      this.$emit("close");
    }
  }
};
</script>

<style lang="scss" scoped>
.lightbox {
  background-color: #071619;
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  backdrop-filter: blur(2px);
  opacity: 0.93;
}

.wrapper {
  // gallery gang wuz here!
  .img {
    opacity: 1;
  }
}
</style>