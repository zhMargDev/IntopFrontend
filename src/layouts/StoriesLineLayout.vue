<template>
    <section id="stories_main">
        <ArrowButton
            :button_width="'50px'"
            :arrow_size="'18px'"
            :arrow_deg="'90deg'"
            @click="leftScroll"
        />

        <div id="stories_box"
            ref="stories"
        >
            <StoryComponent 
                v-for="index in 30" :key="index"
                :viewed="false"
            />
        </div>

        <ArrowButton
            :button_width="'50px'"
            :arrow_size="'18px'"
            :arrow_deg="'270deg'"
            @click="rightScroll"
        />
    </section>
</template>

<script>
import ArrowButton from '@/components/ArrowButton.vue';
import StoryComponent from '@/components/StoryComponent.vue';

export default {
    components: {
        StoryComponent,
        ArrowButton
    },
    methods: {
        rightScroll() {
            // Скроллит направо при нажатии
            const storiesElement = this.$refs.stories;
            const scrollAmount = storiesElement.clientWidth / 2;
            storiesElement.scrollLeft += scrollAmount;
        },
        leftScroll() {
            // Скроллит налево при нажатии
            const storiesElement = this.$refs.stories;
            const scrollAmount = storiesElement.clientWidth / 2;
            storiesElement.scrollLeft -= scrollAmount;
        }
    }
}
</script>


<style scoped>
#stories_box{
    width: 100%;
    display: flex;
    gap: 20px;
    overflow: hidden;
    scroll-behavior: smooth;
}
#stories_main{
    display: grid;
    grid-template-columns: auto 1fr auto;
    align-items: center;
    gap: 40px;
    padding: 0 25px;
}
</style>