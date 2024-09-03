<template>
    <div id="info_main_box"
        :style="{
            border: is_top ? '0px' : '1px solid #b7b7b7'
        }"
    >
        <h4 class="card_title">Водитель на газель категории В</h4>

        <p class="job_type">Платный день - Опыт без опыта</p>

        <div class="grid_2_box"
            style="margin-top: 4px;"
        >
            <p class="user_type">Описание: Работодатель</p>
            <RatingComponent
                style="margin-left: auto;"
                :rating="4.3"
                :is_small="true"
            />
        </div>

        <p class="description">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popul</p>
        
        <div class="grid_2_box">
            <div class="align_center_box">
                <p class="price">{{ formattedNumber(price) }}</p>
            </div>
            <div class="grid_1_box">
                <img src="@/assets/for_delete/userpicture.png" class="owner_avatar" alt="Owner avatar">
                <div class="relative_box">
                    <img src="@/assets/svg_icons/checked.svg" class="checked_icon" alt="Checked icon">
                    <img src="@/assets/for_delete/shoplogo.png" class="shop_logo" alt="Owner avatar">
                </div>
            </div>
        </div>
        
        <div class="grid_2_box">
            <div class="flex_box">
                <img src="@/assets/svg_icons/orange_clock.svg" class="icon" alt="Clock icon">
                <p class="time">{{ formatTimer(time) }}</p>
            </div>
            <button class="send_to_email_btn">Отправить на почту</button>
        </div>
        <div class="grid_2_box" style="margin-top: 10px;">
            <div class="flex_box">
                <img src="@/assets/png_icons/placeholder.png" class="icon" alt="Placeholder icon">
                <p class="location">Узбекистан,</p>
                <p class="location">Ташкент</p>
            </div>
            <div class="flex_box">
                <img src="@/assets/svg_icons/eye.svg" class="icon" alt="Eye icon">
                <p class="views_count">{{ formattedNumber(2332) }}</p>
            </div>
        </div>
    </div>
</template>

<script>
import RatingComponent from '@/components/RatingComponent.vue';

export default{
    components:{
        RatingComponent
    },
    props:{
        is_top: Boolean,
        price: Number,
        time: Number
    },
    methods:{
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
.views_count{
    font-weight: 400;
    font-size: 9px;
    color: rgba(0, 0, 0, 0.8);
}
.location{
    font-weight: 500;
    font-size: 9px;
    color: rgba(0, 0, 0, 0.8);
}
.send_to_email_btn{
    font-weight: 500;
    font-size: 8px;
    color: #FFFFFF;
    background: #129E00;
    border-radius: 3px;
    padding: 4px 8px;
    border: 0;
    cursor: pointer;
    width: max-content;
    margin-left: auto
}
.time{
    font-weight: 500;
    font-size: 10px;
    color: #616161;
}
.icon{
    width: 11px;
}
.flex_box{
    display: flex;
    gap: 5px;
    align-items: center;
}
.align_center_box{
    display: flex;
    align-items: center;
}
.checked_icon{
    position: absolute;
    width: 9px;
    top: 0;
    right: -6px;
}
.relative_box{
    position: relative;
}
.shop_logo{
    width: 48px;
    margin: 0 auto;
}
.grid_1_box{
    display: grid;
    justify-content: center;
    margin-left: auto;
}
.owner_avatar{
    width: 41px;
    height: 41px;
    margin: 0 auto;
}
.price{
    font-weight: 500;
    font-size: 12px;
    color: #000000;
}
.grid_2_box{
    display: grid;
    grid-template-columns: auto 1fr;
}
.description{
    font-weight: 400;
    font-size: 10px;
    color: #000000;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 3;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    margin-top: 6px;
}
.user_type{
    font-weight: 400;
    font-size: 8px;
    color: #000000;
}
.job_type{
    font-weight: 400;
    font-size: 10px;
    color: #000000;
    text-decoration: underline;
}
.card_title {
    font-weight: 700;
    font-size: 12px;
    color: #333333;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: normal;
    height: 36px;
}
#info_main_box{
    position: relative;
    z-index: 5;
    border: 1px solid #b7b7b7;
    border-top: 0;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    padding: 12px 9px;
}
</style>