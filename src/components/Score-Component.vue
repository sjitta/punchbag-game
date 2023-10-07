<template>
    <div class="score">
      <p>Health: {{ health }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      health: Number,
    },
  };
  </script>
  
  <style scoped>
  .score {
    text-align: center;
  }
  </style>