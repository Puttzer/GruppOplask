<template>
  <div class="lightbox" v-if="show == true" @click="closething()">
    <div class="wrapper">
      <img :src="bigImage" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    show: Boolean,
    bigImage: String
  },
  data() {
    return {
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