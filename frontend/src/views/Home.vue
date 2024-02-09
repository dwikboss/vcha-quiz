<template>
  <div class="page home">
    <div class="full-width">
      <div class="content-container">
        <div class="content-holder">
          <div class="blur"></div>
          <img class="logo" src="@/assets/images/logos/vcha-logo.png" alt="" />
          <h1>WHICH<br />VCHA MEMBER ARE YOU?</h1>
          <p>TAKE THE QUIZ TO REVEAL YOUR VCHA BESTIE AND PERSONALITY GEMSTONES</p>
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
    letter-spacing: -5px;
  }

  .full-width {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;

    .content-container {
      width: 100%;
      height: 100%;
      display: flex;

      .blur {
        position: absolute;
        top: 0;
        height: 100%;
        width: 100%;
        backdrop-filter: blur(12px);
        z-index: 0;
      }
      .content-holder {
        background-image: url('@/assets/images/galaxy.webp');
        background-size: cover;
        width: 40%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        gap: 50px;
        position: relative;

        img,
        h1,
        p {
          z-index: 2;
        }

        h1 {
          text-align: center;
          line-height: 0.9em;
        }

        p {
          color: white;
          font-family: 'Poppins';
          font-size: 26px;
          text-align: center;
          width: 50%;
          font-weight: 500;
        }
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
