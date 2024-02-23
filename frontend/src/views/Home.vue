<template>
  <div class="page home">
    <div class="full-width">
      <div class="content-container">
        <div class="content-holder">
          <div class="blur"></div>
          <div class="contents">
            <img class="logo" src="@/assets/images/logos/vcha-logo.png" alt="" />
            <h1>WHICH<br />VCHA MEMBER<br /> ARE YOU?</h1>
            <p>TAKE THE QUIZ TO REVEAL YOUR VCHA BESTIE AND PERSONALITY GEMSTONES</p>
            <button class="btn-main">LET'S ROLL!</button>
          </div>
        </div>
        <Members class="members-component"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Members from '@/components/Members.vue';

export default defineComponent({
  name: 'HomeView',
  components: {
    Members
  },
});
</script>

<style lang="scss" scoped>
.page.home {
  background-color: var(--black);
  height: 100vh;

  h1 {
    color: white;
    letter-spacing: 1px;
    font-size: 5em;
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

      .members-component {
        width: 55%;
      }

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
        width: 45%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        position: relative;

        .contents {
          display: flex;
          flex-direction: column;
          align-items: center;
          gap: 35px;
          z-index: 2;

          .btn-main {
            color: #9765E2;
            background-color: white;
            border: none;
            font-family: 'Poppins';
            border-radius: 999px;
            font-size: 24px;
            font-weight: 700;
            padding: 10px 25px 10px 25px;
          }
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
          font-weight: 400;
        }
      }
    }

    .logo {
      max-width: 350px;
    }
  }
}
</style>
