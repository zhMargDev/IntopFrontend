<template>
    <div id="info_main_box">
        <button class="owner_avatar">
            <img src="@/assets/for_delete/userpicture.png" alt="Owner">
        </button>

        <div class="grid_8gap">
            <div class="grid_2">
                <h4>Студия 35кв/м</h4>
                <p class="selling_type">Б/У</p>
            </div>
            <div class="grid_2">
                <p class="catepgry_name" >Сдам в аренду студия</p>
            </div>
            <div class="grid_2">
                <div class="location_box" >
                    <img src="@/assets/png_icons/placeholder.png" class="placeholder" alt="Placholder icon">
                    <p>Узбекистан,</p>
                    <p>Ташкент</p>
                </div>

                <p class="price_type">Договорная</p>
            </div>

            <div class="grid_2" style="align-items: end;">
                <div class="shop_type">
                    <img src="@/assets/for_delete/shoplogo.png" class="shop_avatar" alt="Shop avatar">
                    <img src="@/assets/svg_icons/checked.svg" class="checked_shop_icon" alt="Checked icon">
                </div>

                <div class="grid_8gap" >
                    <RatingComponent
                        :rating="4.3"
                        :is_small="true"
                    />
        
                    <div class="views_box">
                        <img src="@/assets/svg_icons/dots.svg" alt="Dots icon">
                        <img src="@/assets/svg_icons/eye.svg" alt="Eye icon">
                        <p>438</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import RatingComponent from '@/components/RatingComponent.vue';

export default{
    components:{
        RatingComponent
    }
}
</script>

<style scoped> 
.views_box p{
    font-weight: 400;
    font-size: 8px;
    color: rgba(0, 0, 0, 0.8);
}
.grid_8gap{
    display: grid;
    gap: 8px;
}
.grid_2{
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 8px;
}
.views_box img{
    width: 11px;
    height: 11px;
}
.views_box{
    display: flex;
    gap: 5px;
}
.checked_shop_icon{
    width: 10px;
    height: 10px;
    position: absolute;
    top: 0;
    right: -10px;
}
.shop_avatar{
    max-height: 15px;
    max-width: 90px;
}
.shop_type{
    margin-top: 10px;
    position: relative;
    width: max-content;
}
.price_type{
    font-weight: 500;
    font-size: 7px;
    color: #A0A0A0;
    margin-top: auto;
}
.placeholder{
    width: 10px;
    height: 10px;
}
.location_box p{
    font-weight: 500;
    font-size: 7px;
    line-height: 8px;
    color: rgba(0, 0, 0, 0.8);
}
.location_box{
    display: flex;
    gap: 4px;
    align-items: center;
}
.catepgry_name{
    font-weight: 600;
    font-size: 9px;
    line-height: 11px;
    color: rgba(51, 51, 51, 0.8);
}
.selling_type{
    font-weight: 400;
    font-size: 9px;
    color: rgba(0, 0, 0, 0.8);
}
h4{
    font-weight: 700;
    font-size: 13px;
    line-height: 16px;
    color: #333333;
    white-space: nowrap;
    overflow: hidden;
}
.owner_avatar img{
    width: 100%;
    height: 100%;
}
.owner_avatar{
    padding: 0;
    margin: 0;
    border: 0;
    background: transparent;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 27px;
    height: 27px;
    position: absolute;
    top: -14px;
    right: 10px;
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