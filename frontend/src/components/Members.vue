<template>
    <div class="members"></div>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'Members',
    props: {
    },
});
</script>
  
<style lang="scss" scoped>
    .members {
        height: 100%;
        width: 55%;
        background-image: url('@/assets/images/vcha-members.webp');
        background-position: center center;
        background-size: cover;
    }
</style>