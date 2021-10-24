<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      @btn-click="$emit('toggle-add-task')"
      :text="btnLabel ? 'Close' : 'Add Tasks'"
      :color="btnLabel ? 'darkred' : 'green'"
    />
  </header>
</template>

<script>
import Button from './Button'

export default {
  name: 'Header',
  components: {
    Button,
  },
  props: {
    title: String,
    btnLabel: Boolean,
  },
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
