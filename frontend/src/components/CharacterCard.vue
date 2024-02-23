<template>
    <div class="card-container">
        <div class="member-image">
            djfhjsadfhkj
        </div>
    </div>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';
// import { memberProfiles } from '@/assets/data/members.json';

export default defineComponent({
    name: 'CharacterCard',
    props: {
        memberData: {}
    },
    data() {

    },
    computed: {
    },
    methods: {
        
    },
});
</script>
  
<style lang="scss" scoped>
.card-container {
    background-color: white;
}
</style> 