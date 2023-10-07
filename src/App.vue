<template>
  <div id="app">
    <Punchbag @game-over="handleGameOver" />
    <Score :health="health" />
  </div>
</template>

<script>
import Punchbag from "@/components/Punchbag-Component.vue";
import Score from "@/components/Score-Component.vue";

export default {
  components: {
    Punchbag,
    Score,
  },
  data() {
    return {
      health: 100, // Initial health
    };
  },
  methods: {
    handleGameOver() {
      // Game over logic (e.g., display a message)
      alert("Game Over! Your health is depleted.");
      // You can also reset the game here if needed.
      this.health = 100; // Reset health
    },
  },
};
</script>