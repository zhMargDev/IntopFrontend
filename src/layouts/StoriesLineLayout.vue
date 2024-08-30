<template>
    <section id="stories_main">
        <button 
            class="arrow_button" 
            @click="leftScroll"
        >
            <img src="@/assets/svg_icons/arrow.svg" alt="Arrow icon">
        </button>

        <div id="stories_box"
            ref="stories"
        >
            <StoryComponent 
                v-for="index in 30" :key="index"
                :viewed="false"
            />
        </div>

        <button 
            class="arrow_button" 
            @click="rightScroll"
        >
            <img src="@/assets/svg_icons/arrow.svg" alt="Arrow icon">
        </button>
    </section>
</template>

<script>
import StoryComponent from '@/components/StoryComponent.vue';

export default {
    components: {
        StoryComponent
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
.arrow_button:last-child img{
    rotate: 270deg;
}
.arrow_button:first-child img{
    rotate: 90deg;
}
.arrow_button img{
    width: 100%;
    height: 100%;
}
.arrow_button{
    border: 0;
    background-color: transparent;
    margin: 0;
    padding: 0;
    width: 18px;
    height: 18px;
    cursor: pointer;
}
#stories_main{
    display: grid;
    grid-template-columns: auto 1fr auto;
    align-items: center;
    gap: 40px;
    padding: 0 25px;
}
</style>