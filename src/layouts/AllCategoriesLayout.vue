<template>
    <div id="all_categories_main_box">
        <CategoryGroupComponent
            v-for="(category) in categories" 
            :key="category.id"
            :picture="category.picture"
            :text="category.text"
            :is_selected="category.id === selected_category_id /* Если категория была выбрана то отправиться true */"
            @select_category="select_category_handler(category.id)"
        />
    </div>
</template>

<script>
import CategoryGroupComponent from '@/components/CategoryGroupComponent.vue';

export default{
    components:{
        CategoryGroupComponent
    },
    data(){
        return{
            selected_category_id: 0,
            categories: [
                {
                    id:1,
                    picture: require('@/assets/svg_icons/real_estate.svg'),
                    text: 'Жилье и недвижемость'
                },
                {
                    id:2,
                    picture: require('@/assets/svg_icons/real_estate.svg'),
                    text: 'Жилье и недвижемость'
                },
                {
                    id:3,
                    picture: require('@/assets/svg_icons/real_estate.svg'),
                    text: 'Жилье и недвижемость'
                },
                {
                    id:4,
                    picture: require('@/assets/svg_icons/real_estate.svg'),
                    text: 'Жилье и недвижемость'
                },
                {
                    id:5,
                    picture: require('@/assets/svg_icons/real_estate.svg'),
                    text: 'Жилье и недвижемость'
                },
                {
                    id:6,
                    picture: require('@/assets/svg_icons/real_estate.svg'),
                    text: 'Жилье и недвижемость'
                },
                {
                    id:7,
                    picture: require('@/assets/svg_icons/real_estate.svg'),
                    text: 'Жилье и недвижемость'
                },
            ]
        }
    },
    methods:{
        select_category_handler(category_id){
            // Функция выбора категории
            this.selected_category_id = category_id;
        }
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