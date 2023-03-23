<template>
  <p>
    Reaction time :
    <span :style="{ color: colorRank, fontWeight: 'bold' }">{{ score }}</span>
    ms
  </p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
      colorRank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Ninja Fingers";
      this.colorRank = "#0faf87";
    } else if (this.score < 400) {
      this.rank = "Rapid Reflexes";
      this.colorRank = "#047ac2";
    } else {
      this.rank = "Snail pace...";
      this.colorRank = "red";
    }
  },
};
</script>

<style scoped>
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
.score {
  color: red;
}
</style>
