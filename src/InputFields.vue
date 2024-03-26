<template>
    <div class="input-fields">
      <input type="number" :value="num1" @input="updateNum1" style="background-color: #f3f3f3; border: 1px solid #ccc; width: 30%;">
      <select :value="operator" @change="updateOperator" style="background-color: #f3f3f3; border: 1px solid #ccc; width: 30%;">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      <input type="number" :value="num2" @input="updateNum2" style="background-color: #f3f3f3; border: 1px solid #ccc; width: 30%;">
    </div>
  </template>
  
  <script>
  export default {
    props: {
      num1: Number,
      num2: Number,
      operator: String
    },
    methods: {
      updateNum1(event) {
        this.$emit('update:num1', event.target.value);
      },
      updateNum2(event) {
        this.$emit('update:num2', event.target.value);
      },
      updateOperator(event) {
        this.$emit('update:operator', event.target.value);
      }
    }
  };
  </script>
  
  <style scoped>
  .input-fields {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
  
  input[type="number"], select {
    padding: 8px;
    width: 30%;
  }
  </style>
  