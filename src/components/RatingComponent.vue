<template>
    <div id="rating_main">
        <img
            v-for="index in activeRatinge()" :key="index"
            src="@/assets/svg_icons/yellow_star.svg" 
            alt="Full star icon"
        >
        <img
            v-for="index in notActiveRating()" :key="index"
            src="@/assets/svg_icons/yellow_star.svg" 
            alt="Full star icon"
        >
        <p>{{ rating }}</p>
    </div>
</template>

<script>
export default{
    props:{
        rating: Number
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
    font-size: 12px;
    color: #000000;
    margin-left: 5px;
}
img{
    width: 10px;
    height: 10px;
}
#rating_main{
    display: flex;
    gap: 3px;
    align-items: center;
}
</style>