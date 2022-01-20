<template>
  <input
    :name="inputName"
    :type="inputType"
    :placeholder="place"
    :v-model="inputName"
    :input="handleValidate"
    :blur="handleValidate"
  />
</template>

<script>
//I cannot splitted this component into atom yet, the validate does not work, have to add it in f-form :(

export default {
  name: 'fText',
  props: ['inputName','inputType','place','handleValidate']
}
</script>

<style scoped>
input {
  padding: 10px;
}
</style>