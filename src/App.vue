<template>
  <div class="calculator">
    <h1 style="color: #4fc08d;">Calculadora Aritmética</h1>
    <div class="input-fields">
      <input type="number" v-model.number="num1" @input="calculate" style="background-color: #f3f3f3; border: 1px solid #ccc;">
      <select v-model="operator" @change="calculate" style="background-color: #f3f3f3; border: 1px solid #ccc;">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      <input type="number" v-model.number="num2" @input="calculate" style="background-color: #f3f3f3; border: 1px solid #ccc;">
    </div>
    <div class="result" style="color: #4fc08d;">
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: 'add',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case 'add':
          this.result = this.num1 + this.num2;
          break;
        case 'subtract':
          this.result = this.num1 - this.num2;
          break;
        case 'multiply':
          this.result = this.num1 * this.num2;
          break;
        case 'divide':
          this.result = this.num2 !== 0 ? this.num1 / this.num2 : 'Infinity';
          break;
        default:
          this.result = 0;
      }
    }
  }
};
</script>

<style scoped>
.calculator {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fff; /* Alterado para branco */
  height: 100%; /* Alterado para 100% */
}

.input-fields {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

input[type="number"], select {
  padding: 8px;
  width: 100px;
}

.result {
  font-size: 18px;
}
</style>
