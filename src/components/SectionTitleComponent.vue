<template>
    <div>
        <img :src="icon" alt="Category icon">
        <h3>{{ title }}</h3>
    </div>
</template>

<script>
export default{
    props:{
        title: {
            type: String,
            default: ''
        },
        icon: String
    }
}
</script>

<style scoped>
h3{
    font-weight: 500;
    font-size: 16px;
    color: #282829;
}
img{
    width: 24px;
}
div{
    border-radius: 8px;
    padding: 7px 14px;
    gap: 13px;
    display: flex;
    align-items: center;
    width: max-content;
    margin: 20px 0;
}
</style>
