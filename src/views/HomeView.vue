<template>
  <div style="margin-bottom: 300px;" >
      <GradientBackground
        :padding="'66px 0px'"
      >
        <h2>Продавайте и покупайте вместе с нами</h2>
        <h4>Просто, быстро и эффективно!</h4>

        <SearchLayout
          style="margin-top: 36px;"
          :is_home_page="true"
        />
      </GradientBackground>

      <StoriesLineLayout
        style="margin-top: 25px;"
      />

      <BigBannerLayout/>

      <HomePageLocationLayer/>

      <section
        style="
          padding: 0 20%;
        "
      >
        <SectionTitleComponent
          :title="'Все категории и подкатегории проекта'"
        />

        <AllCategoriesLayout />

        <SectionTitleComponent
          :title="'Самые популярные объявление дня'"
        />
      </section>

      <AnnouncementCardGroup
        :cards_count="5"
      />
  </div>
</template>

<script>
import GradientBackground from '@/components/GradientBackground.vue';
import BigBannerLayout from '@/layouts/BigBannerLayout.vue';
import SearchLayout from '@/layouts/SearchLayout.vue';
import StoriesLineLayout from '@/layouts/StoriesLineLayout.vue';
import HomePageLocationLayer from '@/layouts/HomePageLocationLayer.vue';
import SectionTitleComponent from '@/components/SectionTitleComponent.vue';
import AllCategoriesLayout from '@/layouts/AllCategoriesLayout.vue';
import AnnouncementCardGroup from '@/layouts/AnnouncementCardGroup.vue';

export default{
    components:{
      GradientBackground,
      SearchLayout,
      StoriesLineLayout,
      BigBannerLayout,
      HomePageLocationLayer,
      SectionTitleComponent,
      AllCategoriesLayout,
      AnnouncementCardGroup
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