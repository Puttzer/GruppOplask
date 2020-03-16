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
    border-radius: 3rem;
    height: 4rem;
    width: 34rem;
    font-size: 40px;
    padding: 0 3rem 0 3rem;
    background: rgb(228, 228, 228) url(../assets/icon.svg) left no-repeat;
    background-size: 3rem;
}

</style>