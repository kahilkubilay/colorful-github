<template>
  <MainHeader />
  <MainContent />
  <MainFooter />

</template>

<script>
import MainHeader from './components/Header/MainHeader.vue'
import MainContent from './components/Content/MainContent.vue'
import MainFooter from './components/Footer/MainFooter.vue'


export default {
  name: 'App',
  components: { MainHeader, MainContent, MainFooter }
}
</script>

<style scoped></style>
