<template>
    <div id="story_main">
        <img src="@/assets/svg_icons/checked.svg" class="checked_icon" alt="Checked icon">

        <div class="main_circle"
            :style="{backgroundColor: !viewed ? '#f16a26' : '#a5a5a5'}"
        >
            <div class="circle">
                <div class="image_box">

                </div>
            </div>
        </div>

        <h4 class="username">Tony</h4>

        <RatingComponent
            :rating="rating"
            style="margin: 0 auto;"
        />
    </div>
</template>

<script>
import RatingComponent from '@/components/RatingComponent.vue';
export default{
    props:{
        viewed:{
            type: Boolean,
            default: false   
        },
        rating:{
            type: Number,
            default: 0
        },
    },
    components:{
        RatingComponent
    }
}
</script>

<style scoped>
.username{
    white-space: nowrap;
    font-weight: 600;
    font-size: 14px;
    text-align: center;
    color: #000000;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-align: center;
}
.checked_icon{
    width: 19px;
    height: 19px;
    position: absolute;
    top: 0;
    right: 0px;
}
.image_box{
    width: 100%;
    height: 100%;
    position: relative;
    border-radius: 100px;
    background-color: black;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
}
.circle{
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    border-radius: 100px;
    padding: 3px;
    background-color: white;
}
.main_circle{
    box-sizing: border-box;
    width: 73px;
    height: 73px;
    border-radius: 100px;
    padding: 5px;
    margin: 0 auto;
}
#story_main{
    position: relative;
    min-width: 110px;
    max-width: 110px;
    display: grid;
    cursor: pointer;
}
</style>