<template>
  <main>
    <ul>
      <ColorItem :items="items"/>
    </ul>

    <div class="popup" v-if="firePopup">
      <div class="copied-color-code">
        <span>Copied #{{ selectedColor }} for {{ selectedLabel }}</span>
      </div>
      <div class="agree">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
          <!-- Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc. -->
          <path d="M438.6 105.4c12.5 12.5 12.5 32.8 0 45.3l-256 256c-12.5 12.5-32.8 12.5-45.3 0l-128-128c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0L160 338.7 393.4 105.4c12.5-12.5 32.8-12.5 45.3 0z"/>
        </svg>
      </div>
    </div>
  </main>
</template>

<script>
import ColorItem from './ColorItem.vue'

export default {
  name: 'MainContent',
  components: { ColorItem },
  data() {
    return {
      isActive: false,
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
    firePopUpElement() {
      this.firePopup = true

      setTimeout(() => {
        this.firePopup = false
      }, 2000)
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

.popup {
  width: 100%;
  height: 100%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #f2f2f2;
  animation: example .5s linear 0s 1;
}

@keyframes example {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
.popup div svg {
  width: 3em;
}

.popup span {
  font-family: -apple-system,BlinkMacSystemFont,"Segoe UI","Noto Sans",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji";
  font-size: 1.5em;
}
</style>