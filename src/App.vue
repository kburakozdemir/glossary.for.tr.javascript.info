<template>
  <Title msg="Glossary" />
  <form id="search">Search <input name="query" v-model="searchQuery" /></form>
  <SimpleGrid
    :heroes="gridData"
    :columns="gridColumns"
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
    >
  </p>
</template>

<script>
import json from "./data/glossary.json";

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
      gridColumns: ["id", "en", "tr"],
      gridData: json,
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
</style>
