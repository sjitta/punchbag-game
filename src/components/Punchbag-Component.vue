<template>
    <div class="punchbag" @click="punch">
      <img :src="health > 0 ? 'bag.png' : 'bag-burst.png'" alt="Punchbag" />
      <div class="health-bar">
        <div class="health" :style="{ width: health + '%' }"></div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        health: 100, // Initial health
      };
    },
    methods: {
      punch() {
        if (this.health > 0) {
          this.health -= 10; // Decrease health on each punch
        }
  
        if (this.health <= 0) {
          // Health is out, emit an event or perform game over logic
          this.$emit("game-over");
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .punchbag {
    position: relative;
    width: 200px;
    height: 200px;
    cursor: pointer;
  }
  
  .health-bar {
    position: absolute;
    bottom: 10px;
    left: 10px;
    width: 100%;
    height: 10px;
    background-color: #ccc;
    border: 1px solid #666;
  }
  
  .health {
    height: 100%;
    background-color: #4caf50;
  }
  </style>