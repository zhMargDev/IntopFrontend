<template>
    <div id="rating_main"
        :style="{
            gap: is_small ? '2px' : '3px'
        }"
    >
        <img
            v-for="index in activeRatinge()" :key="index"
            :style="{
                width: is_small ? '8px' : '10px',
                height: is_small ? '8px' : '10px',
                
            }"
            src="@/assets/svg_icons/yellow_star.svg" 
            alt="Full star icon"
        >
        <img
            v-for="index in notActiveRating()" :key="index"
            :style="{
                width: is_small ? '8px' : '10px',
                height: is_small ? '8px' : '10px',
                
            }"
            src="@/assets/svg_icons/gray_star.svg" 
            alt="Full star icon"
        >
        <p
            :style="{
                fontSize: is_small ? '9px' : '12px',
                marginLeft: is_small ? '0px' : '5px',
            }"
        >{{ rating }}</p>
    </div>
</template>

<script>
export default{
    props:{
        rating: Number,
        is_small:{
            type: Boolean,
            default: false
        }
    },
    methods:{
        activeRatinge(){
            return parseInt(this.rating);
        },
        notActiveRating(){
            return 5 - parseInt(this.rating);
        }
    }
}
</script>

<style scoped>
p{
    font-weight: 300;
    color: #000000;
}
#rating_main{
    display: flex;
    gap: 3px;
    align-items: center;
}
</style>