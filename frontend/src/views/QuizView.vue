<template>
    <div class="page quiz">
        <div class="full-width">
            <h1>test</h1>
        </div>
    </div>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'QuizView',
    components: {
    },
    data() {
        return {
        };
    },
    computed: {},
    methods: {
    },
});
</script>
  
<style lang="scss" scoped>
.page.quiz {
    height: 100vh;

    .full-width {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100%;
    }
}
</style>