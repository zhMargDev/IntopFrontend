<template>
    <div>
        <img src="@/assets/svg_icons/categories.svg" alt="Category icon">
        <h3>{{ title }}</h3>
    </div>
</template>

<script>
export default{
    props:{
        title: {
            type: String,
            default: ''
        }
    }
}
</script>

<style scoped>
h3{
    font-weight: 500;
    font-size: 13px;
    color: #FFFFFF;
}
img{
    width: 20px;
}
div{
    background: linear-gradient(90deg, #F16C26 0%, #FEBF1C 100%);
    border-radius: 8px;
    padding: 7px 14px;
    gap: 17px;
    display: flex;
    align-items: center;
    width: max-content;
    margin: 20px 0;
}
</style>
