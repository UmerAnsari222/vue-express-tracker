<template>
  <nav>
    <button class="btn" @click="openModel">
      Add Expense
    </button>
  </nav>
</template>

<script>
export default {
  methods: {
    openModel() {
      this.$emit("show-model");
    },
  },
};
</script>

<style scoped>
nav {
  width: 100%;
  height: 60px;
  background: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}
.btn {
  border: none;
  border-radius: 3px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  background: #42b983;
  color: white;
  padding: 10px 15px;
  cursor: pointer;
}
</style>
