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
          url:
            "https://images.unsplash.com/photo-1497366754035-f200968a6e72?ixlib=rb-1.2.1&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjExOTYwNn0",
          id: 1
        },
        {
          url:
            "https://images.unsplash.com/photo-1497366754035-f200968a6e72?ixlib=rb-1.2.1&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjExOTYwNn0",
          id: 2
        },
        {
          url:
            "https://images.unsplash.com/photo-1497366754035-f200968a6e72?ixlib=rb-1.2.1&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjExOTYwNn0",
          id: 3
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
      max-width: 100px;
    }
  }
}
</style>