<template>
  <div class="blur"></div>
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
  background-size: cover;

  .blur {
    position: absolute;
    top: 0;
    height: 100%;
    width: 100%;
    backdrop-filter: blur(20px);
    z-index: 0;
  }
}

template {
  background-color: red;
}

.page {
  min-height: 100vh;
  height: 100%;
}
</style>
