<template>
  <div class="members">
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
import members from '@/assets/data/members.json';
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
        const selectedMember = members[memberName];
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
  background-position: center center;
  background-size: cover;
  background-size: 110%;

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
}
</style>
