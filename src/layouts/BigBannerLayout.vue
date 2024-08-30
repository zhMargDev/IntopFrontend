<template>
    <section>
        <div id="banner_main">
            <button class="arrow" @click="prevBanner">
                <img src="@/assets/svg_icons/arrow.svg" alt="Arrow icon">
            </button>

            <div id="banner_container" :style="bannerContainerStyle">
                <img 
                    v-for="(banner, index) in banners" 
                    :key="index" 
                    src="@/assets/banner.png"  
                    :alt="'Banner ' + (index + 1)"
                    class="banner-img"
                >
            </div>

            <button class="arrow" @click="nextBanner">
                <img src="@/assets/svg_icons/arrow.svg" alt="Arrow icon">
            </button>
        </div>
    </section>
</template>

<script>
export default {
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
.arrow:last-child img {
    rotate: 270deg;
}
.arrow:first-child img {
    rotate: 90deg;
}
.arrow:last-child {
    right: 35px;
}
.arrow:first-child {
    left: 35px;
}
.arrow img {
    width: 100%;
    height: 100%;
}
.arrow {
    border: 0;
    background-color: transparent;
    padding: 0;
    margin: 0;
    width: 40px;
    height: 40px;
    position: absolute;
    top: 50%;
    transform: translate(0, -50%);
    z-index: 1;
    display: flex;
    justify-content: center;
    align-content: center;
}
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