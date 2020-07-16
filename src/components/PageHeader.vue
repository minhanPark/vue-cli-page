<template>
  <div>
    <h2 class="header">조회조건 검색</h2>
    <h3 class="sub--header">기본 정보관리 > 가맹점 정보 관리</h3>
    <div class="search--wrapper">
      <div class="search--header">
        <h4>조회조건</h4>
      </div>
      <div class="select--wrapper">
        <select v-model="condition">
          <option value="선택없음">선택없음</option>
          <option value="franchiseCode">가맹점코드</option>
          <option value="franchiseName">가맹점명</option>
        </select>
      </div>
      <div class="input--wrapper">
        <input v-model="value" placeholder="입력해주세요." v-on:keyup.enter="handleSearch" />
      </div>
    </div>
    <div class="btn--wrapper">
      <ul class="btn--container">
        <li v-on:click="clearAllValue">
          조건 초기화
          <i class="fas fa-undo"></i>
        </li>
        <li v-on:click="handleSearch">
          조회
          <i class="fas fa-search"></i>
        </li>
      </ul>
    </div>
    <Modal v-if="showModal">
      <h3 slot="header">오류 발생</h3>
      <div slot="body">
        <p>검색 조건 및 검색어를 입력해주세요.</p>
        <button @click="showModal = false">확인</button>
      </div>
    </Modal>
  </div>
</template>

<script>
import Modal from "./common/Modal.vue";

export default {
  data() {
    return {
      condition: "선택없음",
      value: "",
      showModal: false
    };
  },
  methods: {
    handleSearch() {
      if (this.condition === "선택없음" || this.value === "") {
        this.showModal = true;
      } else {
        this.$emit("findLists", this.condition, this.value);
        this.clearValue();
      }
    },
    clearValue() {
      this.condition = "선택없음";
      this.value = "";
    },
    clearAllValue() {
      this.clearValue();
      this.$emit("clearValue");
    }
  },
  components: {
    Modal
  }
};
</script>

<style scoped>
.header {
  font-size: 18px;
  margin: 0.7rem 0;
}
.sub--header {
  font-size: 17px;
  margin: 0.5rem 0;
}
.search--wrapper {
  display: flex;
  align-items: center;
  border: 1px solid #bdc3c7;
  padding: 0.3rem 0.5rem;
}
.search--header h4 {
  margin: 0;
  font-size: 16px;
  padding-right: 1.5rem;
  border-right: 1px solid #bdc3c7;
}
.select--wrapper select {
  font-size: 16px;
  width: 8rem;
  margin: 0 0.3rem;
}
.input--wrapper {
  width: 50%;
}
.input--wrapper input {
  font-size: 15px;
  padding: 0.1rem 0.2rem;
  width: 100%;
}

.btn--container {
  display: flex;
  margin: 8px 0;
  justify-content: flex-end;
}
.btn--container li {
  list-style-type: none;
  cursor: pointer;
  border: 1.5px solid #273c75;
  padding: 0.1rem 0.2rem;
}
.btn--container li:nth-child(2) {
  margin-left: 1rem;
  background-color: #273c75;
  color: white;
}
</style>