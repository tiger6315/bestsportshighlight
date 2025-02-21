<template>
  <div class="container">
    <h1 class="title">BESTSPORTSHIGHLIGHT</h1>
    <div class="widget-container sr-widget-1"></div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  (function(a,b,c,d,e,f,g,h,i){
    a[e]||(i=a[e]=function(){(a[e].q=a[e].q||[]).push(arguments)},i.l=1*new Date,i.o=f,
    g=b.createElement(c),h=b.getElementsByTagName(c)[0],g.async=1,g.src=d,g.setAttribute("n",e),h.parentNode.insertBefore(g,h)
  })(window,document,"script", "https://widgets.sir.sportradar.com/67b84746344f43026b255e94/widgetloader", "SIR", {
      theme: false,
      language: "en"
  });
  
  SIR("addWidget", ".sr-widget-1", "match.scoreboard", { matchId: 52631971 });
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
.widget-container {
  background: #1e1e1e;
  padding: 20px;
  border-radius: 10px;
}
</style>
