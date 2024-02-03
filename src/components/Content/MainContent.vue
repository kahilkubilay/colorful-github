<template>
  <main>
    <ul>
      <ColorItem :items="items" @userSelectedColor="handlePopUp" />
    </ul>

    <PopUp :firePopup="firePopup" :selectedColor="selectedColor" :selectedLabel="selectedLabel" />
  </main>
</template>

<script>
import ColorItem from './ColorItem.vue'
import PopUp from './PopUp.vue'

export default {
  name: 'MainContent',
  components: { ColorItem, PopUp },
  data() {
    return {
      firePopup: false,
      selectedColor: '',
      selectedLabel: '',
      items: [
        {
          'label': 'TypeScript',
          'color': '3178c6',
          'isActive': false
        },
        {
          'label': 'Javascript',
          'color': 'f1e05a',
          'isActive': false
        },
        {
          'label': 'CSS',
          'color': '563d7c',
          'isActive': false
        }
      ]
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
  margin: 0 auto;
  padding: 1em 0;
}

ul {
  display: inherit;
  width: 100%;
  flex-direction: column;
}
</style>