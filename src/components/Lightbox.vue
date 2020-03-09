<template>
  <div class="lightbox" v-if="show == true"></div>
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
            "https://images.unsplash.com/photo-1461988320302-91bde64fc8e4?ixid=2yJhcHBfaWQiOjEyMDd9&&fm=jpg&w=400&fit=max",
          id: 1
        }
      ]
    };
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
</style>