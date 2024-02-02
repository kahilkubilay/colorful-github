<template>
  <header>
    <div class="logo">
      <img src="../asset/colorful-github-logo.png" alt="colorful-github logo">
    </div>
    <div class="propaganda">
      <h2>colorful - github</h2>
      <p>color codes for languages on github</p>
    </div>
  </header>
</template>

<script>
export default {
  name: 'MainHeader'
}
</script>

<style scoped>
header {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1em 0 .5em 0;
  background-color: #f2f2f2;
}
.logo {
  display: inherit;
}
.logo img {
  width: 5em;
}
.propaganda {
  display: inherit;
  flex-direction: inherit;
  align-items: inherit;
  margin-top: 1em;
}

.propaganda h2, .propaganda p {
  font-family: -apple-system,BlinkMacSystemFont,"Segoe UI","Noto Sans",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji";
}

.propaganda h2 {
  font-size: 1.5em;
}

.propaganda p {
  
  text-align: center;
  font-size: 1.2em;
}
</style>
