<template>
  <div class="card-container">
    <div class="member-image-container">
      <div class="member-image" :style="`background-image: url(/src/assets/images/members/${memberData?.member_img})`">
        <div class="top-card">
          <div class="member-intro">
            <p>{{ memberData.name }}</p>
            <p>{{ memberData.birthday }}</p>
          </div>
          <div class="number-circle">
            <p class="member-number">{{ memberData.favorite_number }}</p>
          </div>
        </div>
        <div class="bottom-card">
          <div class="member-basic">
            <p>Favorite Season</p>
            <p>{{ memberData.favorite_season }}</p>
          </div>
          <div class="member-basic">
            <p>Special skills</p>
            <p>{{ memberData.skills }}</p>
          </div>
          <div class="member-basic">
            <p>Birth city</p>
            <p>{{ memberData.birth_city }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import type _IMember from '../interfaces/_IMember';

export default defineComponent({
  name: 'CharacterCard',
  data() {},
  props: {
    memberData: {} as _IMember,
  },
  computed: {},
  methods: {},
});
</script>

<style lang="scss" scoped>
.card-container {
  width: 22vw;
  height: 65vh;
  background-image: url('@/assets/images/spark.gif');
  box-shadow: inset 0 0 0 2000px rgb(74 36 101 / 60%);

  .member-image-container {
    height: 100%;
    padding: 20px;
    .member-image {
      border-radius: 25px;
      background-size: cover;
      background-position: center;
      height: 100%;
      display: flex;
      justify-content: space-between;
      flex-direction: column;

      .top-card {
        display: flex;
        justify-content: center;
        align-items: center;
        justify-content: space-between;
        height: 20%;
        width: 100%;
        padding: 0 30px 0 30px;

        .member-intro {
          color: white;
          font-family: 'Abril Fatface';
          p:first-child {
            font-size: 3rem;
          }

          p:nth-child(2) {
            font-size: 1.2rem;
          }
        }

        .number-circle {
          background-color: white;
          padding: 5px;
          border-radius: 999px;
          width: 60px;
          height: 60px;
          display: flex;
          justify-content: center;
          align-items: center;

          .member-number {
            color: rgb(80, 60, 128);
            font-family: 'Abril Fatface';
            font-size: 1.8rem;
          }
        }
      }

      .bottom-card {
        height: 50%;
        background: rgb(69,65,92);
        background: linear-gradient(180deg, rgba(69,65,92,0) 0%, rgba(73,47,116,1) 100%);
        padding: 35px;
        display: flex;
        flex-direction: column;
        gap: 10px;
        justify-content: flex-end;

        .member-basic {
          p:first-child {
            color: white;
            font-family: 'Poppins';
            font-size: 0.8rem;
          }
          p:nth-child(2) {
            color: white;
            font-family: 'Poppins';
            font-weight: 700;
            font-size: 1.1rem;
          }
        }
      }
    }
  }
}
</style>
