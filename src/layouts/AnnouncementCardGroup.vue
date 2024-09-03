<template>
    <div 
        id="group_main_box"
        :style="{
            gridTemplateColumns: `repeat(${columns_count}, auto)`
        }"
    >
        <AnnouncementCard
            v-for="index in cards_count"
            :key="index"
            :is_top="true"
        />
    </div>
</template>

<script>
import AnnouncementCard from '@/layouts/AnnouncementCard.vue';

export default{
    props:{
        cards_count: Number
    },
    components:{
        AnnouncementCard
    },
    data(){
        return{
            columns_count: 10
        }
    },
    mounted() {
        // Добавляем обработчик события resize при монтировании компонента
        window.addEventListener('resize', this.reset_columns_count);
        // Вызываем функцию сразу, чтобы она сработала при загрузке страницы
        this.reset_columns_count();
    },
    beforeUnmount() {
        // Удаляем обработчик события resize перед уничтожением компонента
        window.removeEventListener('resize', this.reset_columns_count);
    },
    methods:{
        reset_columns_count() {
            const screenWidth = window.innerWidth;
            const availableWidth = screenWidth * 0.7; // 70% of screen width
            const elementWidth = 180;
            const gap = 24;
            const totalElementWidth = elementWidth + gap;

            let count = Math.floor(availableWidth / totalElementWidth);

            // Ensure count is divisible by 2
            if (count % 2 !== 0) {
                count -= 1;
            }

            this.columns_count = count;
            console.log(this.columns_count)
        }
    }
}
</script>

<style scoped>
#group_main_box{
    display: grid;
    justify-content: center;
    gap: 24px;
}
</style>