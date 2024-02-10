<template>
  <footer>
    <a href="https://github.com/kahilkubilay/colorful-github">
      <img src="./asset/github-logo.png" alt="link of the colorful github repo"/>
    </a>

    <a href="https://www.npmjs.com/package/colorful-github">
      <img src="./asset/npm-logo.png" alt="link of the colorful github repo"/>
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
  position: fixed;
  left: 0;
  bottom: 0;
  background-color: #f2f2f2;
  width: 100%;
  padding: 1em;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
}

footer a img {
  width: 2em;
  margin-right: 1em;
  display: inherit;
  vertical-align: center;
}

</style>