<template>
  <div>
    <div>{{newPropsData}}</div>
    <div>
      <input v-model="newPropsData.code" />>
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
</style>