<template>
  <div>
      <p>das ist die Bücherliste</p>
        <div v-html="dummytext">

        </div>
  </div>
</template>

<script>
export default {
    name: 'BookList',
    data() {
        return {
            dummytext : "",
        }
    },
    created () {
        this.$axios.get("api/10/medium/ol/headers/code")
        .then((response) => {
            this.dummytext = response.data
        })
    },
    beforeDestroy(){
        console.log("befordestroy von BookList")
    }
}
</script>

<style>

</style>