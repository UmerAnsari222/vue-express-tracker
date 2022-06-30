<template>
  <Navbar @show-model="toggleModel" />
  <Model
    @model-toggle="toggleModel"
    :status="modelStatus"
    @store-expense="storeExpense"
  />
  <Expenses :allExpenses="expenses" />
</template>

<script>
import Expenses from "./components/Expenses.vue";
import Model from "./components/Model.vue";
import Navbar from "./components/Navbar.vue";
export default {
  components: { Navbar, Model, Expenses },
  name: "App",
  data() {
    return {
      modelStatus: false,
      expenses: {
        balance: 0,
        income: 0,
        expense: 0,
        history: [],
      },
    };
  },
  methods: {
    toggleModel() {
      this.modelStatus = !this.modelStatus;
    },

    storeExpense(payload) {
      const number = parseInt(payload.number);
      if (number > 1) {
        this.expenses = {
          ...this.expenses,
          income: this.expenses.income + number,
          balance: this.expenses.balance + number,
          history: [{ title: payload.title, number }, ...this.expenses.history],
        };
      } else if (number < 1) {
        this.expenses = {
          ...this.expenses,
          expense: this.expenses.expense + number,
          balance: this.expenses.balance + number,
          history: [{ title: payload.title, number }, ...this.expenses.history],
        };
      }
      this.modelStatus = false;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Courier New", Courier, monospace;
}
body {
  background: #fafafa;
}
</style>
