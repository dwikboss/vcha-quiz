<template>
  <div class="page home">
    <div class="full-width">
      <div class="content-container">
        <div class="content-holder">
          <img class="logo" src="@/assets/images/logos/vcha-logo.png" alt="" />
          <h1>WHICH VCHA MEMBER ARE YOU?</h1>
        </div>
        <div class="members-image"></div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomeView',
});
</script>

<style lang="scss" scoped>
.page.home {
  background-color: var(--black);
  height: 100vh;

  h1 {
    color: white;
    letter-spacing: 5px;
  }

  .full-width {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;
    background-color: red;

    .content-container {
      width: 100%;
      height: 100%;
      display: flex;
      .content-holder {
        background-color: rgb(194, 96, 250);
        width: 40%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
      }
      .members-image {
        height: 100%;
        width: 60%;
        background-color: yellow;
        background-image: url('@/assets/images/vcha-members.webp');
        background-position: center center;
        background-size: cover;
      }
    }

    .logo {
      max-width: 350px;
    }
  }
}
</style>
