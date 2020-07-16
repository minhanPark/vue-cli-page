<template>
  <div id="app">
    <PageHeader v-on:findLists="getLists"></PageHeader>
    <PageLists v-bind:data="searchedList"></PageLists>
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
  },
  data() {
    return {
      franchiseLists: [
        {
          code: "M2000",
          loc: "국내",
          franchiseName: "스타벅스",
          registrationNum: "555-222-111",
          ceo: "스벅",
          status: "오픈",
          address: "해운대해변로 304",
          email: "starbucks@co.kr",
          registrationDate: "2020-04-01"
        },
        {
          code: "M2001",
          loc: "국내",
          franchiseName: "어벤더치",
          registrationNum: "123-456-789",
          ceo: "어더",
          status: "중지",
          address: "수영강변로 300",
          email: "avendurch@co.kr",
          registrationDate: "2020-04-24"
        },
        {
          code: "M2002",
          loc: "해외",
          franchiseName: "이태리커피",
          registrationNum: "128-222-321",
          ceo: "이태리",
          status: "해지",
          address: "이태리 바닷가",
          email: "italia@co.kr",
          registrationDate: "2020-06-02"
        },
        {
          code: "M2003",
          loc: "해외",
          franchiseName: "아프리카커피",
          registrationNum: "784-222-111",
          ceo: "아커",
          status: "중지",
          address: "초원로 301",
          email: "africa@co.kr",
          registrationDate: "2020-07-01"
        }
      ],
      searchedList: {}
    };
  },
  methods: {
    getLists(condition, value) {
      const temp = condition === "franchiseCode" ? "code" : "franchiseName";
      const lists = this.franchiseLists.filter(list => list[temp] === value);
      this.searchedList = lists[0];
      console.log(this.searchedList);
    }
  }
};
</script>

<style>
</style>
