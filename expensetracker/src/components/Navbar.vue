<template>
  <div class="navdiv">
    <h1>Expense Tracker</h1>
    <nav>
      <button class="button" @click="openModel">Add Expense</button>
    </nav>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  methods: {
    openModel() {
      this.$emit("model-show");
    },
  },
};
</script>

<style scoped>
.navdiv {
  width: 100%;
  height: 80px;
  background: #fff;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
}

.button {
  position: fixed;
  top: 4%;
  right: 2%;
  border: none;
  border-radius: 3px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  background: #80002a;
  color: #fff;
  padding: 10px 15px;
  cursor: pointer;
  font-size: 1.2rem;
  outline: none;
}

h1 {
  font-family: sans-serif;
  color: #4e001a;
  margin-left: 5px;
}
</style>