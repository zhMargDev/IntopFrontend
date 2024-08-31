<template>
    <div 
        class="mask_main"
        :style="{zIndex: z_index}"
        :class="{'golder_border': is_top}"
    >
        <TopTicket 
            v-if="is_top"
            style="
                position: absolute;
                left: -7px;
                top: 13px;
            "
        />
    </div>
</template>

<script>
import TopTicket from './TopTicket.vue';

export default{
    components:{
        TopTicket
    },
    props:{
        is_top: {
            type: Boolean,
            default: false
        },
        z_index:{
            type: Number,
            default: 5
        },
    },
    
}
</script>

<style scoped>
.golder_border{
    border-color: #ffdd1f !important;
}
.mask_main{
    width: calc(100% - 4px);
    height: calc(100% - 4px);
    position: absolute;
    background-color: 100%;
    top: 0;
    left: 0;
    border: 2px solid transparent;
}
</style>