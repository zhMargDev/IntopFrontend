<template>
    <div class="card">
        <div class="card_image_box">
            <AnnouncementPictureMask 
                :is_top="false"
                :z_index="5"
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
                    <button v-if="time > 0">
                        <img src="@/assets/svg_icons/orange_clock.svg" alt="Clock">
                    </button>
                    <p v-if="time > 0">{{ formatTimer(time) }}</p>
                    <button>
                        <img src="@/assets/svg_icons/orange_heart.svg" alt="Clock">
                    </button>
                </div>


                <h4 
                    class="price"
                    :style="{
                        'color': is_top ? '#ffdd1f' : 'white'
                    }"
                >{{ formattedNumber(price) }}</h4>
            </div>
        </div>
        
        <AnnouncementCardInformationComponent/>
    </div>
</template>

<script>
import AnnouncementCardInformationComponent from '@/components/AnnouncementCardInformationComponent.vue';
import AnnouncementPictureMask from '@/components/CardIsInTop.vue';

export default {
    components:{
        AnnouncementPictureMask,
        AnnouncementCardInformationComponent
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
        formattedNumber(value) {
            // Возвращает отформотированную ценру добавляя тип валюты
            return `${value.toLocaleString('ru-RU')} ${this.$store.state.currency}` ;
        },
        formatTimer(time) {
            const secondsInMinute = 60;
            const secondsInHour = 60 * secondsInMinute;
            const secondsInDay = 24 * secondsInHour;
    
            const days = Math.floor(time / secondsInDay);
            const hours = Math.floor((time % secondsInDay) / secondsInHour);
            const minutes = Math.floor((time % secondsInHour) / secondsInMinute);
    
            let formattedTime = '';
            if (days > 0) {
                formattedTime += days + ' д ';
            }
            if (hours > 0) {
                formattedTime += hours + ' ч ';
            }
            if (minutes > 0) {
                formattedTime += minutes + ' м ';
            }
    
            return formattedTime.trim();
        }
    }
}
</script>

<style scoped>
.buttons_box p{
    font-weight: 500;
    font-size: 8px;
    color: #FFFFFF;
    margin-top: 2px;
}
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
.price{
    font-weight: 500;
    font-size: 13px;
    position: absolute;
    bottom: 10px;
    left: 10px;
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