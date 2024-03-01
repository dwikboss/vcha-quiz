<template>
  <div class="members">
    <div class="social-icons">
      <div class="social-icon">
        <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="instagram"
          class="svg-inline--fa fa-instagram SocialLinkButton_icon__jgBol" role="img" xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 448 512">
          <path fill="currentColor"
            d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z">
          </path>
        </svg>
      </div>
      <div class="social-icon">
        <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="x-twitter"
          class="svg-inline--fa fa-x-twitter SocialLinkButton_icon__jgBol" role="img" xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 512 512">
          <path fill="currentColor"
            d="M389.2 48h70.6L305.6 224.2 487 464H345L233.7 318.6 106.5 464H35.8L200.7 275.5 26.8 48H172.4L272.9 180.9 389.2 48zM364.4 421.8h39.1L151.1 88h-42L364.4 421.8z">
          </path>
        </svg>
      </div>
      <div class="social-icon">
        <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="tiktok"
          class="svg-inline--fa fa-tiktok SocialLinkButton_icon__jgBol" role="img" xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 448 512">
          <path fill="currentColor"
            d="M448,209.91a210.06,210.06,0,0,1-122.77-39.25V349.38A162.55,162.55,0,1,1,185,188.31V278.2a74.62,74.62,0,1,0,52.23,71.18V0l88,0a121.18,121.18,0,0,0,1.86,22.17h0A122.18,122.18,0,0,0,381,102.39a121.43,121.43,0,0,0,67,20.14Z">
          </path>
        </svg>
      </div>
      <div class="social-icon">
        <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="youtube"
          class="svg-inline--fa fa-youtube SocialLinkButton_icon__jgBol" role="img" xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 576 512">
          <path fill="currentColor"
            d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z">
          </path>
        </svg>
      </div>
    </div>
    <div class="member-navigation">
      <div class="member-list">
        <p v-for="(member, index) in members" :key="index" @click="selectMember(member)">{{ member }}</p>
      </div>
    </div>
    <div class="member-card-container">
      <CharacterCard v-if="selectedMember" :memberData="selectedMember" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import members from '@/assets/data/members';
import CharacterCard from '@/components/CharacterCard.vue';
import type _IMember from '../interfaces/_IMember';

export default defineComponent({
  name: 'Members',
  components: {
    CharacterCard,
  },
  data() {
    return {
      members: Object.keys(members),
      selectedMember: {} as _IMember,
    };
  },
  computed: {},
  methods: {
    selectMember(memberName: string) {
      if (members.hasOwnProperty(memberName)) {
        const selectedMember = members[memberName] as unknown as _IMember;
        console.log(selectedMember);
        this.selectedMember = selectedMember;
      } else {
        console.log(`Member '${memberName}' not found.`);
        return null;
      }
    },
  },
});
</script>

<style lang="scss" scoped>
.members {
  height: 100%;
  background-image: url('@/assets/images/vcha-members.webp');
  background-size: cover;
  background-size: 60%;
  background-attachment: fixed;
  background-position: 100% 50%;

  .social-icons {
    display: flex;
    flex-direction: column;
    gap: 8px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    right: 25px;

    .social-icon {
      background-color: white;
      border-radius: 50%;
      width: 30px;
      height: 30px;
      display: flex;
      justify-content: center;
      align-items: center;

      svg {
        width: 15px;
        height: auto;
        color: rgb(124, 32, 32);
      }
    }
  }

  .member-card-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90vh;

  }

  .member-navigation {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 10vh;

    .member-list {
      display: flex;
      gap: 25px;

      p {
        color: white;
        text-transform: uppercase;
        font-family: 'Poppins';
        font-weight: 500;
        font-size: 1.5rem;

        &:hover {
          text-shadow: 0px 0px 5px #a742ce;
          cursor: pointer;
        }
      }
    }
  }
}</style>
