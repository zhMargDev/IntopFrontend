<template>
    <div id="all_categories_main_box">
        <CategoryGroupComponent
            v-for="index in 10" :key="index"
        />
    </div>
</template>

<script>
import CategoryGroupComponent from '@/components/CategoryGroupComponent.vue';

export default{
    components:{
        CategoryGroupComponent
    }
}
</script>

<style scoped>

#all_categories_main_box{
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 30px;
    align-items: start;
}
</style>