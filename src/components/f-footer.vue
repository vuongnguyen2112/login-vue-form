<template>
  <div class="footer-form">
    <button>Cancel</button>
    <p>Forgot <a href="javascript:void(0)">password?</a></p>
  </div>
</template>

<script>

export default {
  name: 'fFooter',
}
</script>

<style scoped>
.footer-form {
  margin-top: 20px;
  padding: 30px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: calc(100% - 40px);
  background-color: #ccc;
}

button {
  border: none;
  padding: 7px 14px;
  background-color: #f13a3a;
  font: inherit;
  color: #fff;
  font-size: 14px;
}

button:hover {
  cursor: pointer;
  opacity: 0.8;
}

p {
  font-size: 14px;
}
</style>