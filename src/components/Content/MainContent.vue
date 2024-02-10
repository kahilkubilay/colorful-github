<template>
  <main>
    <ul>
      <ColorItem v-for="(item, index) in items" :key="index" :item="item" @userSelectedColor="handlePopUp" />
    </ul>

    <PopUp :firePopup="firePopup" :selectedColor="selectedColor" :selectedLabel="selectedLabel" />
  </main>
</template>

<script>
import ColorItem from './ColorItem.vue'
import PopUp from './PopUp.vue'
import colorSource from './../asset/colorSource.json'

export default {
  name: 'MainContent',
  components: { ColorItem, PopUp },
  data() {
    return {
      firePopup: false,
      selectedColor: '',
      selectedLabel: '',
      items: colorSource
    }
  },
  methods: {
    handlePopUp(userSelectedOption) {
      this.selectedColor = userSelectedOption.selectedColor
      this.selectedLabel = userSelectedOption.selectedLabel
      this.firePopup = true

      setTimeout(() => {
        this.firePopup = false
      }, 1000)
    }
  }
}
</script>

<style scoped>
main {
  display: flex;
  justify-content: center;
  width: 50%;
  margin: 1em auto;
  padding: 1em 0 5em 0;
}

ul {
  display: inherit;
  width: 100%;
  flex-direction: column;
}

@media only screen and (max-width: 768px) {
  main {
    width: 90%;
  }
}
</style>