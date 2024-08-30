<template>
    <div id="categories_main">
        <div class="selected_box">
            <p>Товар или услуга</p>
            <img 
                :src="is_orange_arrow ? require('@/assets/svg_icons/orange_arrow.svg')
                    : require('@/assets/svg_icons/arrow.svg')" 
                alt="Orange arrow"
            >
        </div>
    </div>
</template>

<script>
export default{
    props:{
        is_orange_arrow: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style scoped>
.selected_box img{
    width: 11px;
    height: 11px;
}
.selected_box p{
    font-weight: 500;
    font-size: 11px;
    color: #000000;
}
.selected_box{
    display: flex;
    align-items: center;
    gap: 10px;
    cursor: pointer;
}
</style>