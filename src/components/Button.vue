<template>
  <button
    @click="handleClick()"
    :style="{ backgroundColor: color }"
    class="btn"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: String,
    color: String,
  },
  methods: {
    handleClick() {
      this.$emit('btn-click')
    },
  },
}
</script>

<style></style>
