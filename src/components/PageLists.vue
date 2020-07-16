<template>
  <div>
    <div class="list-container">
      <table>
        <tr>
          <th>가맹점 CODE</th>
          <th>가맹점명</th>
          <th>가맹점 구분</th>
          <th>사업자등록번호</th>
          <th>가맹점 상태</th>
          <th>등록일자</th>
        </tr>
        <tr v-if="isEmptyList(data) === true">
          <td colspan="6">데이터가 없습니다.</td>
        </tr>
        <tr v-else class="item" v-on:click="handleClick(data.code)">
          <td>{{data.code}}</td>
          <td>{{data.franchiseName}}</td>
          <td>{{data.loc}}</td>
          <td>{{data.registrationNum}}</td>
          <td>{{data.status}}</td>
          <td>{{data.registrationDate}}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  props: ["data"],
  methods: {
    isEmptyList(param) {
      return Object.keys(param).length === 0 && param.constructor === Object;
    },
    handleClick(code) {
      console.log("clicked");
      this.$emit("getC", code);
    }
  }
};
</script>

<style scoped>
.list-container {
  margin: 2rem 0;
}
table {
  width: 100%;
  table-layout: fixed;
  border-collapse: collapse;
  border: 1.5px solid #bdc3c7;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
}
th,
td {
  padding: 15px;
  text-align: center;
  vertical-align: center;
}
th {
  height: 20px;
  background-color: #273c75;
  color: white;
}
.item:hover {
  background-color: #ecf0f1;
  cursor: pointer;
}
</style>