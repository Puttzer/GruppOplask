<template>
  <div class="home">
    <Search  @search="getImages"/>
    <Gallery :images="images"/>
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

data () {

return {
    images: [],
}

    },

methods:{
getImages(searchWord){

const url = `https://api.unsplash.com/search/photos?page=1&query=${searchWord}&client_id=mNBE4VyLg2ReXfZj46B7KH19_XZbuzuRXZubUrrtBCw`
        
    fetch(url)
        .then((resp) => resp.json())
        .then((data) => {
          console.log(data.results)
          this.images = data.results;
            })
            .catch(function(error) {
                console.log(error);
                
         })
         
        }
    }

};


</script>


