<template>
  <li v-for="item in items" :key="item.color" @mouseover="item.isActive = true" @mouseleave="item.isActive = false"
    @click="copyColorCode(item.color, item.label)" :style="[{
      'background-color': item.isActive ? `#${item.color}` : '',
      'color': item.isActive ? `#fff` : ''
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
  props: ['items'],
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

.symbol span {
  width: 1em;
  height: 1em;
  border-radius: 100%;
}
</style>