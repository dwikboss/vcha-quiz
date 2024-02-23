<template>
  <div class="card-container">
    <div class="member-image-container">
      <div class="member-image" :style="`background-image: url(/src/assets/images/members/${memberData?.member_img})`">
        <div class="top-card">
          <p class="member-name">{{ memberData.name }}</p>
          <div class="number-circle">
            <p class="member-number">{{ memberData.favorite_number }}</p>
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
  border-radius: 10px;
  background-image: url('@/assets/images/spark.gif');
  box-shadow: inset 0 0 0 2000px rgb(57 76 147 / 70%);

  .member-image-container {
    height: 100%;
    padding: 20px;
    .member-image {
      border-radius: 25px;
      background-size: cover;
      background-position: center;
      height: 100%;
      display: flex;
      justify-content: center;
      .top-card {
        display: flex;
        justify-content: center;
        height: 12%;
        align-items: center;
        width: 100%;
        justify-content: space-between;
        padding: 35px 35px 0 35px;

        .member-name {
          color: white;
          font-family: 'Abril Fatface';
          font-weight: 100;
          font-size: 3rem;
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
    }
  }
}
</style>
