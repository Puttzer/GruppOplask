<template>
<section>
<input class="searchstyle" type="text" placeholder="Search" v-model="search" v-on:keyup.enter="submit">

</section>

</template>

<script>


export default {
    name: "Search",
data () {

return {
    search: ''
}

    },

methods:{
    submit() {
        this.$emit("search", this.search)
    }

    }
}

</script>

<style lang="scss">

.searchstyle {
    outline: none;
    border: none;
    padding: 0 0 0 0rem;
    border-radius: 3rem;
    height: 4rem;
    width: 40rem;
    font-size: 32px;
    background-color: rgb(238, 236, 236);
    padding: 0 2rem 0 2rem;

}

</style>