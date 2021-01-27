<template>
  <Title msg="Glossary" />
  <form id="search">Search <input name="query" v-model="searchQuery" /></form>
  <SimpleGrid
    :gridData="gridData"
    :gridColumns="gridColumns"
    :filter-key="searchQuery"
  />
 <Footer />
</template>

<script>
import data from "./data/glossary.json";

import Title from "./components/Title.vue";
import Footer from "./components/Footer.vue";
import SimpleGrid from "./components/SimpleGrid.vue";
export default {
  name: "App",
  components: {
    SimpleGrid,
    Title,
    Footer,
  },
  data: function () {
    // Table headers are populated from the data itself
    var gColumns = Object.keys(data.data[0]);
    // Alternative
    // var gColumns = data.colums;

    return {
      searchQuery: "",
      gridData: data.data,
      gridColumns: gColumns,
    };
  },
};
</script>

<style>
html {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*,
*:before,
*:after {
  -webkit-box-sizing: inherit;
  -moz-box-sizing: inherit;
  box-sizing: inherit;
}

body {
  font-family: "Helvetica Neue", Arial, sans-serif;
  font-size: 1rem;
  color: #444;
}
</style>
