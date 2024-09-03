<template>
    <div class="card"
        :style="{
            border: is_top ? '2px solid yellow' : '0px'
        }"
    >
        <div class="card_image_box">
            <TopTicket
                style="
                    z-index: 5;
                    top: 13px;
                    left: -10px;
                    position: absolute;
                "

                v-if="is_top"
            />
            <img src="@/assets/for_delete/picture_2.webp" class="card_picture" alt="Card picture">
            <div 
                class="blurred_background"
                :style="{
                    background: `url('${picture()}')`
                }"
            ><!--Длюр заднего фона той же картинкой, если картинка не полностью влезает в рамки--></div>
            <div 
                class="white_overlay"
                :style="{
                    backgroundColor: $store.state.background
                }"
            ></div>


            <div 
                style="
                    position: absolute;
                    z-index: 5;
                    width: 100%;
                    height: 100%;
                "
            >
                <div class="buttons_box">
                    <button>
                        <img src="@/assets/svg_icons/orange_heart.svg" alt="Clock">
                    </button>
                </div>
            </div>
        </div>
        
        <AnnouncementCardInformationComponent
            :is_top="is_top"
            :price="price"
            :time="time"
        />
    </div>
</template>

<script>
import AnnouncementCardInformationComponent from '@/components/AnnouncementCardInformationComponent.vue';
import TopTicket from '@/components/TopTicket.vue';

export default {
    props:{
        is_top: {
            type: Boolean,
            default: false
        }
    },
    components:{
        AnnouncementCardInformationComponent,
        TopTicket
    },
    data(){
        return{
            time: 22222,
            price: 2104120
        }
    },
    methods:{
        picture(){
            return require('@/assets/for_delete/picture_2.webp')
        },
    }
}
</script>

<style scoped>
.buttons_box{
    display: flex;
    justify-content: center;
    position: absolute;
    right: 10px;
    top: 10px;
    gap: 7px;
}
button img{
    width: 15px;
    height: 15px;
}
button{
    border: 0;
    background-color: transparent;
    margin: 0;
    padding: 0;
}
.card_picture {
    height: 100%;
    object-fit: cover; /* Масштабирует изображение, чтобы заполнить контейнер */
    position: relative;
    z-index: 3; /* Убедитесь, что основное изображение находится поверх размытого фона */
}

.card_image_box {
    width: 100%;
    height: 130px;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
}

.blurred_background {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    background-size: cover; /* Масштабирует фоновое изображение, чтобы заполнить контейнер */
    z-index: 1; /* Убедитесь, что размытый фон находится под основным изображением */
}

.white_overlay {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    opacity: 0.5;
    z-index: 2; /* Убедитесь, что белый фон находится поверх размытого изображения, но под основным изображением */
}
.card:hover{
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
.card {
    width: 190px;
    position: relative;
    transition: 300ms;
    cursor: pointer;
}
</style>