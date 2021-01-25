<template>
  <Title msg="Glossary" />
  <form id="search">Search <input name="query" v-model="searchQuery" /></form>
  <SimpleGrid
    :gridData="gridData"
    :gridColumns="gridColumns"
    :filter-key="searchQuery"
  />
  <p>
    <small
      ><em
        >Inspired by official
        <a
          href="https://vuejs.org/v2/examples/grid-component.html"
          target="_blank"
          >Grid Component Example</a
        ></em
      ></small
    >.
  </p>
</template>

<script>
import data from "./data/glossary.json";

import Title from "./components/Title.vue";
import SimpleGrid from "./components/SimpleGrid.vue";
export default {
  name: "App",
  components: {
    SimpleGrid,
    Title,
  },
  data: function () {
    return {
      searchQuery: "",
      gridColumns: data.columns,
      gridData: data.data,
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
  font-family: 'Helvetica Neue', Arial, sans-serif;
  font-size: 1rem;
  color: #444;
}
</style>
