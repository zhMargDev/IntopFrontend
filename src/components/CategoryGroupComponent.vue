<template>
    <div class="cateogry_box">
        <div 
            class="category_image_box"
            :style="{
                backgroundColor: is_selected ? '#FFF9E9' : '#EBECEC'
            }"
            @click="request_to_select_category"
        >

        <img :src="picture" alt="Category icon">

        </div>
        <div class="category_title_box">
            <h4
                :style="{
                    /* Цвет текста становится оранжевым если категория была выбрана */
                    color: is_selected ? '#F16A26' : '#707070'
                }"
            >{{ text }}</h4>
        </div>
    </div>
</template>

<script>
export default{
    props:{
        is_selected: {
            type: Boolean,
            default: false
        },
        picture: String,
        text: String
    },
    methods:{
        request_to_select_category(){
            // Выполняет запрос на выбор данной категории
            this.$emit('select_category')
        }
    }
}
</script>

<style scoped>
.subcategories_box p:hover{
    color: #F16A26;
    text-decoration: underline;
}
.subcategories_box p{
    font-weight: 500;
    font-size: 11px;
    color: #969696;
    transition: 200ms;
    cursor: pointer;
}
.subcategories_box{
    display: grid;
    gap: 4px;
    transition: 300ms;
    overflow-y: scroll;
    overflow-x: hidden;
    scrollbar-width: thin; /* Для Firefox */
    scrollbar-color: #F16A26 transparent; /* Для Firefox */
}
/* Для браузеров на основе WebKit (Chrome, Safari) */
.subcategories_box::-webkit-scrollbar {
    width: 3px; /* Толщина скроллбара */
}

.subcategories_box::-webkit-scrollbar-thumb {
    background-color: #F16A26; /* Цвет ползунка скроллбара */
}

.subcategories_box::-webkit-scrollbar-track {
    background-color: transparent; /* Цвет трека скроллбара */
}
h4{
    font-weight: 500;
    font-size: 12px;
    line-height: 12px;
    color: #707070;
    cursor: pointer;
    transition: 300ms;
}
.category_title_box img{
    width: 14px;
}
.category_title_box{
    display: flex;
    gap: 6px;
    margin-bottom: auto;
    justify-content: center;
}
.category_image_box{
    width: 110px;
    height: 110px;
    border-radius: 110px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    overflow: hidden;
    transition: 200ms;
}
.cateogry_box{
    display: grid;
    gap: 10px;
    height: max-content;
    margin-bottom: auto;
    cursor: pointer;
}
</style>