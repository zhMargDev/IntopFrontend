<template>
    <section>
        <div id="banner_main">
            <ArrowButton
                :button_width="'130px'"
                :arrow_size="'30px'"
                :arrow_deg="'90deg'"
                :is_absolute="true"
                @click="prevBanner"
            />

            <div id="banner_container" :style="bannerContainerStyle">
                <img 
                    v-for="(banner, index) in banners" 
                    :key="index" 
                    src="@/assets/banner.png"  
                    :alt="'Banner ' + (index + 1)"
                    class="banner-img"
                >
            </div>
            <ArrowButton
                :button_width="'130px'"
                :arrow_size="'30px'"
                :arrow_deg="'270deg'"
                :is_absolute="true"
                @click="nextBanner"
                style="right: 0;"
            />
        </div>
    </section>
</template>

<script>
import ArrowButton from '@/components/ArrowButton.vue';

export default {
    components:{
        ArrowButton
    },
    data() {
        return {
            banner_number: 0,
            banners: [
                '@/assets/banner.png',
                '@/assets/banner.png',
                '@/assets/banner.png'
            ],
            autoScrollInterval: null
        }
    },
    computed: {
        bannerContainerStyle() {
            return {
                transform: `translateX(-${this.banner_number * 100}%)`
            };
        }
    },
    methods: {
        nextBanner() {
            this.stopAutoScroll();
            this.banner_number = (this.banner_number + 1) % this.banners.length;
            this.startAutoScroll();
        },
        prevBanner() {
            this.stopAutoScroll();
            this.banner_number = (this.banner_number - 1 + this.banners.length) % this.banners.length;
            this.startAutoScroll();
        },
        startAutoScroll() {
            this.autoScrollInterval = setInterval(() => {
                this.banner_number = (this.banner_number + 1) % this.banners.length;
            }, 6000);
        },
        stopAutoScroll() {
            clearInterval(this.autoScrollInterval);
        }
    },
    mounted() {
        this.startAutoScroll();
    },
    beforeUnmount() {
        this.stopAutoScroll();
    }
}
</script>

<style scoped>
#banner_main {
    width: 70vw;
    height: calc(70vw / 2.2);
    margin: 0 auto;
    position: relative;
    overflow: hidden;
}
#banner_container {
    display: flex;
    transition: transform 1s;
}
.banner-img {
    width: 100%;
    height: 100%;
    flex-shrink: 0;
}
section {
    margin-top: 50px;
}
</style>