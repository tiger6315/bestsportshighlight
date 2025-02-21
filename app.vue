<template>
  <div class="container">
    <h1 class="title">BESTSPORTSHIGHLIGHT</h1>
    <div class="widget-container">
      <iframe
        src="https://widgets.sir.sportradar.com/67b84746344f43026b255e94/match.scoreboard?matchId=52631971"
        width="600"
        height="400"
        frameborder="0"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

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
.widget-container {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #1e1e1e;
  padding: 20px;
  border-radius: 10px;
}
</style>
