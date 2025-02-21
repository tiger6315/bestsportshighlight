<template>
  <div class="container">
    <h1 class="title">BESTSPORTSHIGHLIGHT</h1>
    <div class="grid">
      <div v-for="(match, index) in matches" :key="index" :id="'sr-widget-' + index" class="widget-container">
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const matches = ref(["52631971", "52631972", "52631973", "52631974"]);

onMounted(() => {
  const script = document.createElement("script");
  script.src = "https://widgets.sir.sportradar.com/sportradar/widgetloader";
  script.async = true;
  document.body.appendChild(script);

  script.onload = () => {
    if (window.SIR) {
      matches.value.forEach((match, index) => {
        window.SIR('addWidget', `#sr-widget-${index}`, 'match.lmtPlus', { matchId: match });
      });
    }
  };
});
</script>

<style scoped>
.container {
  text-align: center;
  padding: 20px;
  background: #121212;
  color: white;
  min-height: 100vh;
}
.title {
  font-size: 36px;
  font-weight: bold;
  text-transform: uppercase;
  color: #ffcc00;
  margin-bottom: 20px;
}
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  padding: 20px;
}
.widget-container {
  background: #1e1e1e;
  padding: 20px;
  border-radius: 10px;
}
</style>
