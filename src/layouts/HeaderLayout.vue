<template>
    <header>
        <LogoComponent/>
        <SellOnIntop
            style="margin-left: 40px;"
        />
        <LanguageLayout
            style="margin-left: auto;"
        />

        <img src="@/assets/svg_icons/add.svg" id="add" alt="Add icon">
        <AddItemButton/>
        <ProfileComponent
            style="margin-left: 10px;"
        />
    </header>
</template>

<script>
import LogoComponent from '@/components/LogoComponent.vue'
import SellOnIntop from '@/components/SellOnIntop.vue';
import LanguageLayout from './LanguageLayout.vue';
import AddItemButton from '@/components/AddItemButton.vue';
import ProfileComponent from '@/components/ProfileComponent.vue';

export default{
    components:{
        LogoComponent,
        SellOnIntop,
        LanguageLayout,
        AddItemButton,
        ProfileComponent
    }
}
</script>

<style scoped>
#add{
    width: 21px;
    height: 21px;
    margin: auto 10px auto 50px;
    cursor: pointer;
}
header{
    display: flex;
    padding: 0 130px;
    height: 70px;
    align-items: center;
}
</style>