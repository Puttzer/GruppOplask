<template>
<section>
<input class="searchstyle" type="text" v-model="search" v-on:keyup.enter="submit">

</section>

</template>

<script>


export default {
    name: "Search",
data:() => ({

return: {

    images: [],
    baseurl: `https://api.unsplash.com/search/photos?page=1&query=office&client_id=xIJxifBLKfQ8_NIf_DtYTV2PDygh-oXGyu7ki-qQ-Uk`,
    search: ''
}

    }),

methods:{

submit(){
const url = `https://api.unsplash.com/search/photos?page=1&query=${this.search}&client_id=xIJxifBLKfQ8_NIf_DtYTV2PDygh-oXGyu7ki-qQ-Uk`
        
    fetch(url)
        .then((resp) => resp.json())
        .then(function(data) {
            let images = data.results;
            this.$emit("search", images)

            })
            .catch(function(error) {
                console.log(error);
         })
        }
    }
}

</script>

<style lang="scoped">
.searchstyle {
    border-radius: 60%;
}

</style>