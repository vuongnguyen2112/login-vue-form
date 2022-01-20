<template>
  <span class="text-errors" v-if="errorString.length">
    {{ errorString[0] }}
  </span>
</template>

<script>

export default {
  name: 'fError',
  props: ["errorString"],
}
</script>

<style scoped>
.text-errors {
  color: red;
  font-style: italic;
}
</style>