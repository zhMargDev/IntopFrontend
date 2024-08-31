<template>
    <div class="cateogry_box">
        <div 
            class="category_image_box"
            @click="is_open = !is_open"
        >
        </div>
        <div class="main_category_box">
            <img src="@/assets/svg_icons/arrow.svg" alt="Arrow">
            <h4
                @click="is_open = !is_open"
            >Жильё и недвижимость</h4>
        </div>

        <div 
            class="subcategories_box"
            :style="{
                maxHeight: is_open ? '200px' : '0px'
            }"
        >
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
            <p>Продам недвижимость</p>
        </div>
    </div>
</template>

<script>
export default{
    data(){
        return{
            is_open: false
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
}
.main_category_box img{
    width: 14px;
}
.main_category_box{
    display: flex;
    gap: 6px;
    margin-bottom: auto;
}
.category_image_box{
    width: 110px;
    height: 110px;
    background: #EBECEC;
    border-radius: 110px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    overflow: hidden;
}
.cateogry_box{
    display: grid;
    gap: 10px;
    height: max-content;
    margin-bottom: auto;
}
</style>