<template>
  <div id="app">
    <full-page />
  </div>
</template>

<script>
import FullPage from './fullpage/FullPage.vue'
export default {
  name: "App",
  components: {
    FullPage
  },
};
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@700;900&display=swap');
body{
  background: linear-gradient(45deg, #4e59f3, #6c46e8);
  font-family: "Roboto", Helvetica, Arial;
}
</style>