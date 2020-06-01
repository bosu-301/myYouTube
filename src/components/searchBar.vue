<template>
  <div>
    <input type="search" @keypress.enter="onInput">
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {
    onInput(event) {
      // 위로 이벤트와 값을 쏜다

      this.$emit('input-search', event.target.value)
      event.target.value = ''
    }
  }
}
</script>

<style>

</style>