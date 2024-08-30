<template>
    <div id="language_main">
        <p>Русский (RU)</p>
        <SwitchComponent
            :is_language="true"
        ></SwitchComponent>
    </div>
</template>

<script>
import SwitchComponent from '@/components/SwitchComponent.vue';

export default{
    components:{
        SwitchComponent
    }
}
</script>

<style scoped>
p{
    font-weight: 600;
    font-size: 12px;
    color: #F16A26;
    white-space: nowrap;
}
#language_main{
    display: flex;
    align-items: center;
    gap: 8px;
}
</style>