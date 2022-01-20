<template>
    <input type="submit" value="Login" />
</template>

<script>

export default {
  name: 'fButton',
}
</script>

<style scoped>
input[type="submit"] {
  border: none;
  margin: 0;
  padding: 10px;
  width: auto;
  font: inherit;
  background-color: #17aa6e;
}
input[type="submit"]:hover {
  cursor: pointer;
  opacity: 0.8;
}
.form-control input[type="submit"] {
  margin-top: 12px;
  color: #fff;
}
</style>