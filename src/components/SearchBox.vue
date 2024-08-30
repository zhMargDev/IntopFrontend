<template>
    <div id="search_box">
        <img src="@/assets/svg_icons/orange_magnifier.svg" alt="Magnifier icon">
        <input 
            type="text"
            placeholder="Что ищем..."
            v-model="search_text"
            @input="emitSearchText"
        >
    </div>
</template>

<script>
export default{
    data(){
        return{
            search_text: ''
        }
    },
    methods:{
        emitSearchText(){
            // Возвращает написанный текст
            this.$emit('search_text', this.search_text)
        }
    }
}
</script>

<style scoped>
input:focus{
    outline: none;
}
input{
    width: 100%;
    border: 0;
    background-color: transparent;
    font-weight: 500;
    font-size: 11px;
    color: #000000;
}
img{
    width: 13px;
    height: 13px;
}
#search_box{
    display: flex;
    gap: 10px;
    align-items: center;
    width: 100%;
}
</style>