<template>
  <div class="container">
    <h1 class="title">BESTSPORTSHIGHLIGHT</h1>
    <div class="grid">
      <div v-for="(match, index) in matches" :key="index" class="widget-container sr-widget-1">
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const matches = ref(["match_1", "match_2", "match_3", "match_4"]);

onMounted(() => {
  (function(a,b,c,d,e,f,g,h,i){
    a[e]||(i=a[e]=function(){(a[e].q=a[e].q||[]).push(arguments)},i.l=1*new Date,i.o=f,
    g=b.createElement(c),h=b.getElementsByTagName(c)[0],g.async=1,g.src=d,g.setAttribute("n",e),h.parentNode.insertBefore(g,h)
  })(window,document,"script", "https://widgets.sir.sportradar.com/lmtdemo/widgetloader", "SIR", {
      theme: false, // using custom theme
      language: "en"
  });
  
  SIR("addWidget", ".sr-widget-1", "match.preview", {matchId: 52631971});
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
