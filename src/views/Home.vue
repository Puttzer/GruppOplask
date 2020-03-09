<template>
  <div class="home">
    <Search @search="getImages" />
    <Gallery :images="images" />
    <button @click="prevPage">prev</button>
    <button @click="nextPage">next</button>
    <button @click="firstPage">first</button>
  </div>
</template>

<script>
// @ is an alias to /src
import Gallery from "../components/Gallery";
import Search from "../components/Search";

export default {
  name: "Home",
  components: {
    Gallery,
    Search
  },

  data() {
    return {
      images: [],
      page: 1,
      search: ""
    };
  },

  methods: {
    getImages(searchWord) {
      console.log(this.page);
      this.search = searchWord;
      const url = `https://api.unsplash.com/search/photos?page=${this.page}&per_page=9&query=${searchWord}&client_id=mNBE4VyLg2ReXfZj46B7KH19_XZbuzuRXZubUrrtBCw`;

      fetch(url)
        .then(resp => resp.json())
        .then(data => {
          console.log(data);
          this.images = data.results;
        })
        .catch(function(error) {
          console.log(error);
        });
    },

    prevPage() {
      if (this.page !== 1) this.page--;
      console.log(this.page);
      this.getImages(this.search);
    },
    nextPage() {
      if (this.page < 12) this.page++;
      console.log(this.page);
      this.getImages(this.search);
    },
    firstPage() {
      this.page = 1;
      console.log(this.page);
      this.getImages(this.search);
    }
  }
};
</script>


