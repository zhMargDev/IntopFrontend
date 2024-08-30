<template>
    <div v-if="is_language"
        @click="is_russian = !is_russian"
    >
        <img 
            :src="is_russian ? require('@/assets/png_icons/ru-flag.png')
            : require('@/assets/png_icons/uz-flag.png')"
            :style="{
                'left': is_russian ? '2px' : '18px'
            }"
        alt="Flag">
    </div>
</template>

<script>
export default{
    props:{
        is_language: Boolean
    },
    data(){
        return{
            is_russian: true
        }
    }
}
</script>

<style scoped>
div{
    width: 33px;
    height: 16px;
    background: #595959;
    border-radius: 100px;
    position: relative;
    cursor: pointer;
}
img{
    width: 12px;
    height: 12px;
    position: absolute;
    top: 2px;
    transition: 300ms;
}
</style>