<template>
    <div
        :style="{
            'padding': padding
        }"
    >
        <slot>

        </slot>
    </div>
</template>

<script>
export default{
    props:{
        padding: String
    }
}
</script>

<style scoped>
div{
    width: 100%;
    background: linear-gradient(90deg, #F16C26 0%, #FEBE1C 69.13%);
}
</style>