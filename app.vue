<template>
  <div class="container">
    <h1 class="title">BESTSPORTSHIGHLIGHT</h1>
    <div class="grid">
      <div v-for="(match, index) in matches" :key="index" :id="'sr-widget-' + index" class="widget-container sr-widget">
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const matches = ref(["52631971", "52631972", "52631973", "52631974"]);

onMounted(() => {
  const script = document.createElement("script");
  script.src = "https://widgets.sir.sportradar.com/67b84746344f43026b255e94/widgetloader";
  script.async = true;
  document.body.appendChild(script);

  script.onload = () => {
    if (window.SIR) {
      matches.value.forEach((match, index) => {
        window.SIR('addWidget', `#sr-widget-${index}`, 'match.scoreboard', { matchId: match });
      });
    }
  };
});
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Roboto:300,400,500,700,900&subset=latin,latin-ext");

.sr-bb {
  font-family: "Roboto", "Noto", "Helvetica Neue", "Helvetica", "Arial", sans-serif;
  text-align: left;
  background: #FFFFFF;
}

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

.sr-bb .srt-base-1 {
  background-color: transparent;
  color: #000000;
  border-color: rgba(0, 0, 0, 0.12);
}

.sr-bb .srt-base-1-win {
  background-color: transparent;
  color: #00003c;
  border-color: #00003c;
}

.sr-bb .srt-base-1-lose {
  background-color: transparent;
  color: #ff0000;
  border-color: #ff0000;
}

.sr-bb .srt-primary-1 {
  background-color: transparent;
  color: #FF0000;
  border-color: #FF0000;
}
</style>
