<template >
  <li v-if="item.color" @mouseover="isActive = true" @mouseleave="isActive = false"
    @click="copyColorCode(item.color, item.label)" :style="[{
      'background-color': isActive ? `#${item.color}` : '',
      'color': isActive ? `#fff` : ''
    }]">
    <div class="symbol">
      <span :style="[{ 'background-color': `#${item.color}` }]"></span>
    </div>
    <div class="label">
      <span>{{ item.label }}</span>
    </div>
    <div class="color">
      <span>#{{ item.color }}</span>
    </div>
  </li>
</template>

<script>
export default {
  name: 'ColorItem',
  props: ['item'],
  data() {
    return {
      isActive: false,
      firePopup: false
    }
  },
  emits: ['userSelectedColor'],
  methods: {
    copyColorCode(code, label) {
      navigator.clipboard.writeText(`#${code}`)

      this.$emit('userSelectedColor', {
        'selectedColor': code,
        'selectedLabel': label
      })

      console.info(`selected ${code} color code`)
    }
  }
}
</script>

<style>
li {
  display: inherit;
  justify-content: space-between;
  align-items: center;
  margin-bottom: .5em;
  border-radius: .5em;
  background-color: #f2f2f2;
  padding: 1em;
  cursor: pointer;
}

li div {
  display: flex;
  flex: 1 1 0;
  justify-content: center;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Noto Sans", Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
  font-size: 1.1em;
}

.label span {
  text-align: center;
}

.symbol span {
  width: 1em;
  height: 1em;
  border-radius: 100%;
  border: 2px solid #f2f2f2;
}
</style>