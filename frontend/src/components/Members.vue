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

export default defineComponent({
    name: 'Members',
    components: {
        CharacterCard
    },
    data() {
        return {
            members: Object.keys(members),
            selectedMember: null as String | null
        };
    },
    computed: {

    },
    methods: {
        selectMember(memberName: string) {
            this.selectedMember = memberName;
            console.log(this.selectedMember);
        }
    }
});
</script>
  
<style lang="scss" scoped>
    .members {
        height: 100%;
        background-image: url('@/assets/images/vcha-members.webp');
        background-position: center center;
        background-size: cover;

        .member-navigation {
            display: flex;
            justify-content: center;
            padding: 25px 0 0 0;
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
                        text-shadow: 0px 0px 5px #A742CE;
                        cursor: pointer;
                    }
                }
            }
        }
    }
</style>