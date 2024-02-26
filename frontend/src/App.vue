<template>
  <RouterView />
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({});
</script>

<style lang="scss">
#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-image: url('@/assets/images/cloth.jpg');
}

template {
  background-color: red;
}

.page {
  min-height: 100vh;
  height: 100%;
}
</style>
