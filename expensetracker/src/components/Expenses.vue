<template>
  <div class="expenses moneydiv">
    <div class="balance">
      <span>Balance</span>
      <p>Rs. {{ allExpenses.balance }}</p>
    </div>
    <div class="income moneydiv">
      <span>Income</span>
      <p>Rs. {{ allExpenses.income }}</p>
    </div>
    <div class="expense moneydiv">
      <span>Expense</span>
      <p>Rs. {{ allExpenses.expense }}</p>
    </div>
  </div>

  <div
    class="history"
    v-for="history in allExpenses.history"
    :key="history.title"
    :class="[history.number > 0 ? 'border-green' : 'border-red']"
  >
    <div class="history_title">{{ history.title }}</div>
    <div class="history_number">{{ history.number }} Rs</div>
  </div>
</template>

<script>
export default {
  name: "Expenses",
  props: ["allExpenses"],
};
</script>

<style scoped>
body {
  font-family: sans-serif;
}

.expenses {
  width: 1400px;
  margin: 70px auto;
  display: flex;
  justify-content: space-between;
}

span {
  font-family: sans-serif;
  position: absolute;
  top: 0;
  left: 0;
  color: #fff;
  font-size: 1.2rem;
  padding: 10px;
  border-radius: 5px 0 5px 0;
}

.balance {
  background: #fff;
  margin: auto 20px;
  padding: 20px;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.2);
  width: 400px;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  border-radius: 5px;
  border-bottom: 4px solid #42b983;
}

.income {
  background: #fff;
  margin: auto 20px;
  padding: 20px;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.2);
  width: 400px;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  border-radius: 5px;
  border-bottom: 4px solid #ffd035;
}

.expense {
  background: #fff;
  margin: auto 20px;
  padding: 20px;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.2);
  width: 400px;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  border-radius: 5px;
  border-bottom: 4px solid #ce0000;
}

.expense span {
  background: #ce0000;
}

.balance span {
  background: #42b983;
}

.income span {
  background: #ffd035;
}

p {
  font-family: sans-serif;
  font-size: 2rem;
}

.history {
  width: 800px;
  margin: 15px auto;
  background: #fff;
  padding: 12px;
  display: flex;
  animation: animate 0.5s ease-out;
}

@keyframes animate {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.history_title {
  font-family: sans-serif;
  width: 80%;
  font-size: 1.2rem;
}

.history_number {
  font-family: sans-serif;
  width: 30%;
  text-align: right;
  font-size: 1.2rem;
}

.border-green {
  border-left: 3px solid #42b983;
}

.border-red {
  border-left: 3px solid #d4075d;
}
</style>
