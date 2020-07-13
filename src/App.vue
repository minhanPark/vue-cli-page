<template>
  <div id="app">
    <PageHeader></PageHeader>
    <PageLists></PageLists>
    <PageDetail></PageDetail>
  </div>
</template>

<script>
import PageHeader from "./components/PageHeader.vue";
import PageLists from "./components/PageLists.vue";
import PageDetail from "./components/PageDetail.vue";

export default {
  name: "App",
  components: {
    PageHeader,
    PageLists,
    PageDetail
  }
};
</script>

<style>
</style>
