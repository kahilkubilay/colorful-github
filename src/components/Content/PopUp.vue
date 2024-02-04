<template>
  <div class="popup" v-if="firePopup">
    <div class="copied-color-code">
      <span>Copied #{{ selectedColor }} for {{ selectedLabel }}</span>
    </div>
    <div class="agree">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
        <!-- Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc. -->
        <path
          d="M438.6 105.4c12.5 12.5 12.5 32.8 0 45.3l-256 256c-12.5 12.5-32.8 12.5-45.3 0l-128-128c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0L160 338.7 393.4 105.4c12.5-12.5 32.8-12.5 45.3 0z" />
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PopUp',
  props: ['firePopup', 'selectedColor', 'selectedLabel']
}
</script>

<style scoped>
.popup {
  width: 100%;
  height: 100%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  position: fixed;
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
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Noto Sans", Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
  font-size: 1.5em;
}
</style>