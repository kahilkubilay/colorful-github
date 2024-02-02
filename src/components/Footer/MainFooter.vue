<template>
  <footer>
    <a href="https://github.com/kahilkubilay/colorful-github">
      <img src="../asset/colorful-github-logo.png" alt="link of the colorful github repo"/>
    </a>
  </footer>
</template>

<script>
export default {
  name: 'MainFooter'
}
</script>

<style scoped>
footer {
  position: absolute;
  left: 0;
  bottom: 0;
  background-color: #f2f2f2;
  width: 100%;
  padding: 1em;
  text-align: center;
}

footer a img {
  width: 2em;
}

</style>