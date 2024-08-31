<template>
    <div>
        <div id="choose_location_main_box">
            <div id="backgroudn_color_line"></div>
            <div id="indicate_location_box">
                <img src="@/assets/png_icons/placeholder.png" class="placeholder_icon" alt="Placeholder icon">
                <p>Указать локацию</p>
                <div class="circle">
                    <img src="@/assets/svg_icons/arrow.svg" alt="Arrow icon">
                </div>
            </div>
        </div>

        <div id="locations_main_box">
            <div id="locations_box">    
                <div class="title_box">
                    <h3>Выберите город или страну</h3>
                    <div class="country_box">
                        <img src="@/assets/svg_icons/orange_placeholder.svg" alt="Placeholder">
                        <p>Узбекистан</p>
                        <img src="@/assets/svg_icons/orange_arrow.svg" alt="Arrow">
                    </div>
                </div>

                <div class="regions_and_cities_box">
                    <div class="city_box">
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                    </div>
                    <div class="city_box">
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                    </div>
                    <div class="city_box">
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                        <div>
                            <h4>Кашкадарьинская область</h4>
                        </div>
                    </div>
                </div>
            </div>
            <MapComponent/>
        </div>
    </div>
</template>

<script>
import MapComponent from '@/components/MapComponent.vue';

export default{
    components:{
        MapComponent
    }
}
</script>

<style scoped>
.city_box h5{
    font-weight: 400;
    font-size: 15px;
    color: #595959;
}
.city_box h4{
    font-weight: 400;
    font-size: 15px;
    color: #303030;
}
.city_box img{
    width: 12px;
}
.city_box{
    display: grid;
    gap: 10px;
}
.regions_and_cities_box{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
}
h3{
    font-weight: 600;
    font-size: 18px;
}
.country_box p {
    font-weight: 600;
    font-size: 18px;
    color: #F16A26;
    position: relative; /* Для позиционирования псевдоэлемента */
}
.country_box p::after {
    content: '';
    position: absolute;
    left: 0;
    bottom: 0px; /* Смещение вниз на 3 пикселя */
    width: 100%;
    height: 2px; /* Толщина линии */
    background-color: #F16A26; /* Цвет линии */
}
.country_box img:last-child{
    width: 13px;
    height: 13px;
}
.country_box img:first-child{
    width: 21px;
    height: 21px;
}
.country_box{
    display: flex;
    gap: 5px;
    align-items: center;
}
.title_box{
    display: grid;
    grid-template-columns: 1fr auto;
    margin-bottom: 20px;
}
#locations_box{
    background-color: #F3F3F3;
    padding: 20px;
    border-radius: 10px;
}
#locations_main_box{
    display: grid;
    grid-template-columns: 1fr auto;
    padding: 0 20%;
    gap: 20px;
}
#backgroudn_color_line{
    width: 100%;
    height: 7px;
    background: linear-gradient(90deg, #F16C26 0%, #FEBE1C 69.13%);
    position: absolute;
    z-index: 1;
    top: 50%;
    left: 0;
    transform: translate(0, -50%);
}
.circle img{
    width: 11px;
    height: 11px;
    filter: invert(1);
}
.circle{
    width: 23px;
    height: 23px;
    background-color: black;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 20px;
}
p{
    font-weight: 500;
    font-size: 18px;
    color: #949494;
}
.placeholder_icon{
    width: 26px;
    height: 26px;
}
#indicate_location_box{
    background: #FFFFFF;
    border: 1px solid #F16A26;
    border-radius: 26px;
    padding: 16px 28px;
    display: flex;
    gap: 30px;
    align-items: center;
    justify-content: center;
    position: relative;
    z-index: 2;
}
#choose_location_main_box{
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    margin: 20px 0;
}
</style>