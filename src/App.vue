<template>
  <div class="container">
    <fImage/>
    <fForm/>
    <fFooter/>
  </div>
</template>

<script>
import fForm from './components/f-form.vue';
import fImage from './components/f-image.vue';
import fFooter from "./components/f-footer.vue";

export default {
  name: 'App',
  components: {
    fForm,
    fImage,
    fFooter
  }
}
</script>

<style scoped>
  .container {
  max-width: 1200px;
  margin: 0 auto;
  border: 20px solid #999999;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}


</style>

<style>
  body {
    font-family: "Roboto", sans-serif;
  }
</style>
