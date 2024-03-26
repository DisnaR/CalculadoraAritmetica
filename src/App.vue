<template>
  <div class="calculator">
    <h1 style="color: #4fc08d; font-size: 2rem;">Calculadora Aritmética</h1>
    <InputFields :num1="num1" :num2="num2" :operator="operator" @update:num1="num1 = $event" @update:num2="num2 = $event" @update:operator="operator = $event" />
    <ResultDisplay :result="result" />
  </div>
</template>

<script>
import InputFields from './InputFields.vue';
import ResultDisplay from './ResultDisplay.vue';

export default {
  components: {
    InputFields,
    ResultDisplay
  },
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: 'add',
      result: 0
    };
  },
  watch: {
    num1: 'calculate',
    num2: 'calculate',
    operator: 'calculate'
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case 'add':
          this.result = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case 'subtract':
          this.result = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case 'multiply':
          this.result = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case 'divide':
          this.result = parseFloat(this.num2) !== 0 ? parseFloat(this.num1) / parseFloat(this.num2) : 'Infinity';
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
  max-width: 90%;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fff;
  height: 100%;
}
</style>
