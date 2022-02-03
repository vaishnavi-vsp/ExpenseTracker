<template>
  <div v-if="status">
    <div class="model" @click.self="toggle">
      <div class="model_container">
        <div class="model_form">
          <form @submit.prevent="addExpense">
            <div class="model_group">
              <h3>Add Expense</h3>
            </div>
            <div class="model_group">
              <input
                type="text"
                class="model_control"
                placeholder="Title"
                v-model="title"
              />
            </div>
            <div class="model_group">
              <input
                type="number"
                class="model_control"
                placeholder="Expense"
                v-model="number"
              />
            </div>
            <div class="model_group">
              <input type="submit" value="Add Expense" class="button" />
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Model",
  props: ["status"],
  data() {
    return {
      title: "",
      number: null,
    };
  },
  methods: {
    toggle() {
      this.$emit("model-toggle");
    },
    addExpense() {
      this.$emit("store-expense", { title: this.title, number: this.number });
      this.title = "";
      this.number = "";
    },
  },
};
</script>

<style scoped>
.model {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  background: rgba(0, 0, 0, 0.5);
  justify-content: center;
  align-items: center;
  font-family: sans-serif;
  z-index: 1;
}

.model_container {
  background: #fff;
  width: 450px;
  padding: 20px;
  border-radius: 5px;
}

.model_group {
  margin: 15px 0;
  font-size: 1.05rem;
}

.model_control {
  border: 1px solid silver;
  border-left: none;
  border-right: none;
  border-top: none;
  width: 100%;
  padding: 7px 0;
  font-size: 1.05rem;
  outline: none;
}

.button {
  border: none;
  border-radius: 3px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  background: #80002a;
  color: #fff;
  padding: 10px 15px;
  cursor: pointer;
  font-size: 1.05rem;
  width: 100%;
  outline: none;
}
</style>