<template>
  <div class="container">
    <h1 class="title">NBA Live Match Tracker</h1>

    <div class="grid">
      <div v-for="match in matches" :key="match.id" class="widget-container">
        <div :id="'sr-widget-' + match.id"></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const matches = ref([
  { id: "match_1" },
  { id: "match_2" },
  { id: "match_3" }
]);

onMounted(() => {
  const script = document.createElement("script");
  script.src = "https://widgets.sir.sportradar.com/sportradar/widgetloader";
  script.async = true;
  document.body.appendChild(script);

  script.onload = () => {
    if (window.SIR) {
      matches.value.forEach((match) => {
        window.SIR('addWidget', `#sr-widget-${match.id}`, 'match.lmtPlus', { matchId: match.id });
      });
    }
  };
});
</script>

<style scoped>
.container {
  text-align: center;
  padding: 20px;
}
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}
.widget-container {
  background: #1e1e1e;
  padding: 10px;
  border-radius: 10px;
}
.title {
  font-size: 24px;
  margin-bottom: 20px;
}
</style>
