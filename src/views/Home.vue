<template>
  <div class="home">
    <Search />
    <Gallery />
  </div>
</template>

<script>
// @ is an alias to /src
import Gallery from "../components/Gallery";
import Search from "../components/Gallery";

export default {
  name: "Home",
  components: {
    Gallery,
    Search
  }
};
</script>
