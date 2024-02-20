<template>
    <div class="members">
        <div class="member-navigation">
            <div class="member-list">
                <p>Kaylee</p>
                <p>Camila</p>
                <p>KG</p>
                <p>Kendall</p>
                <p>Lexi</p>
                <p>Savanna</p>
            </div>
        </div>
    </div>
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
                }
            }
        }
    }
</style>