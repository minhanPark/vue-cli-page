<template>
  <div>
    <div>{{newPropsData}}</div>
    <div class="detail--wrapper">
      <div class="detail--wrapper__header">
        <a>가맹점 정보</a>
      </div>
      <div class="detail--wrapper__body">
        <div class="body__wrapper">
          <h4 class="body__header">가맹점 정보</h4>
          <ul class="btn--container">
            <li>
              신규가맹점
              <i class="fas fa-plus"></i>
            </li>
          </ul>
        </div>
        <div class="body__body">
          <div>
            <label for="code">가맹점 CODE</label>
            <input id="code" />
          </div>
          <div>
            <label for="loc">가맹점 구분</label>
            <input id="loc" />
          </div>
          <div>
            <label for="name">가맹점명</label>
            <input id="name" />
          </div>
        </div>
        <div class="body__body">
          <div>
            <label for="registrationNum">사업자등록번호</label>
            <input id="registrationNum" />
          </div>
          <div>
            <label for="ceo">대표자</label>
            <input id="ceo" />
          </div>
          <div>
            <label for="status">가맹점 상태</label>
            <input id="status" />
          </div>
        </div>
        <div class="body__body">
          <div>
            <label for="address">사업장 주소</label>
            <input id="address" />
          </div>
          <div>
            <label for="email">Email 주소</label>
            <input id="email" />
          </div>
        </div>
        <div class="body__body">
          <div>
            <label for="homepage">홈페이지 주소</label>
            <input id="homepage" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["propsdata"],
  data() {
    return {
      newPropsData: { ...this.propsdata }
    };
  },
  watch: {
    propsdata(newVal) {
      this.newPropsData = newVal;
    }
  }
};
</script>

<style>
.detail--wrapper {
  border: 1.5px solid #bdc3c7;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
}
.detail--wrapper__header {
  border-bottom: 1.5px solid #bdc3c7;
  padding: 0 4px;
}
.detail--wrapper__header a {
  padding: 8px 16px;
  display: inline-block;
  border-bottom: 1.5px solid #273c75;
  color: #273c75;
}
.body__wrapper {
  display: flex;
  padding: 4px;
  align-items: center;
}
.body__header {
  margin: 4px;
  margin-right: 8px;
  background-color: #74b9ff;
  padding: 8px 16px;
}
.btn--container {
  margin: 0;
  padding: 0;
}
.btn--container li {
  list-style-type: none;
  cursor: pointer;
  border: 1.5px solid #273c75;
  background-color: #273c75;
  color: white;
  padding: 4px 8px;
}
</style>