<template>
  <div>
      <GradientBackground
        :padding="'66px 0px'"
      >
        <h2>Продавайте и покупайте вместе с нами</h2>
        <h4>Просто, быстро и эффективно!</h4>

        <SearchLayout
          style="margin-top: 36px;"
          :is_home_page="true"
        ></SearchLayout>
      </GradientBackground>
  </div>
</template>

<script>
import GradientBackground from '@/components/GradientBackground.vue';
import SearchLayout from '@/layouts/SearchLayout.vue';

export default{
    components:{
      GradientBackground,
      SearchLayout
    }
}
</script>

<style scoped>
h4{
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  color: #FFFFFF;
  text-align: center;
}
h2{
  font-weight: 600;
  font-size: 31px;
  color: #FFFFFF;
  text-transform: uppercase;
  text-align: center;
}
</style>