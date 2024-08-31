<template>
    <div id="group_main_box">
        <AnnouncementCard
            v-for="index in cards_count"
            :key="index"
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
    }
}
</script>

<style scoped>
#group_main_box{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 24px;
}
</style>