<template>
  <div>
    <div class="expenses">
      <div class="balance">
        <span>Balance</span>
        <p>{{ allExpenses.balance }} Rs</p>
      </div>
      <div class="income">
        <span>Income</span>
        <p>{{ allExpenses.income }} Rs</p>
      </div>
      <div class="expense">
        <span>Expense</span>
        <p>{{ allExpenses.expense }} Rs</p>
      </div>
    </div>
    <div
      class="history"
      v-for="history in allExpenses.history"
      :key="history"
      :class="[history.number > 0 ? 'border__green' : 'border__red']"
    >
      <div class="history__title">{{ history.title }}</div>
      <div class="history__number">{{ history.number }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["allExpenses"],
};
</script>

<style scoped>
.expenses {
  width: 800px;
  margin: 70px auto;
  display: flex;
  justify-content: space-between;
}
.balance {
  background: #fff;
  width: 200px;
  height: 150px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  border-bottom: 4px solid orange;
}
.balance span {
  position: absolute;
  top: 0;
  left: 0;
  background: orange;
  color: #fff;
  font-size: 12px;
  padding: 5px;
}

.income {
  background: #fff;
  width: 200px;
  height: 150px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  border-bottom: 4px solid #42b983;
}
.income span {
  position: absolute;
  top: 0;
  left: 0;
  background: #42b983;
  color: #fff;
  font-size: 12px;
  padding: 5px;
}

.expense {
  background: #fff;
  width: 200px;
  height: 150px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  border-bottom: 4px solid #d4075d;
}
.expense span {
  position: absolute;
  top: 0;
  left: 0;
  background: #d4075d;
  color: #fff;
  font-size: 12px;
  padding: 5px;
}
p {
  font-size: 20px;
  font-weight: bold;
}

.history {
  width: 800px;
  margin: 15px auto;
  background: #fff;
  padding: 12px;
  display: flex;
}
.history__title {
  width: 70%;
  font-weight: bold;
  text-transform: capitalize;
}
.history__number {
  width: 30%;
  text-transform: capitalize;
  text-align: right;
  font-weight: bold;
}
.border__green {
  border-left: 3px solid #42b983;
}
.border__red {
  border-left: 3px solid #d4075d;
}
</style>
