<template>
    <button 
        class="arrow_button" 
        :style="{
            width: button_width,
            height: button_height,
            position: is_absolute ? 'absolute' : 'relative',
            zIndex: z_index,
        }"
    >
        <img 
            :style="{
                width: arrow_size,
                height: arrow_size,
                rotate: arrow_deg
            }"
            src="@/assets/svg_icons/arrow.svg" 
            alt="Arrow icon"
        >
    </button>
</template>

<script>
export default{
    props:{
        button_width: {
            type: String,
            default: '20px'
        },
        button_height: {
            type: String,
            default: '100%'
        },
        arrow_size: {
            type: String,
            default: '100%'
        },
        arrow_deg: {
            type: String,
            default: '0deg'
        },
        is_absolute:{
            type: Boolean,
            default: false
        },
        z_index:{
            type: Number,
            default: 1
        },
    }
}
</script>

<style scoped>
.arrow_button{
    border: 0;
    background-color: transparent;
    margin: 0;
    padding: 0;
    cursor: pointer;
    top: 0;
}
</style>