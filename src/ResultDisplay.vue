<template>
    <div class="result" style="color: #4fc08d;">
      <p>Resultado: {{ result }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      result: {
        type: Number,
        default: 0
      }
    }
  };
  </script>
  
  <style scoped>
  .result {
    font-size: 1.5rem;
  }
  </style>
  