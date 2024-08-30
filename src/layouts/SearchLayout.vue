<template>
    <div>
        <div 
            id="search_main" 
            :style="{
                gridTemplateColumns: is_home_page ? '1fr auto' : 'auto 1fr auto auto'
            }"
        >

            <div 
                id="search_background"
                v-if="is_home_page" 
            >
                <img src="@/assets/svg_icons/categories.svg" id="categiries_icon" alt="Categories icon">
                <CategoriesFilterComponent
                    :is_orange_arrow="true"
                ></CategoriesFilterComponent>
                <SearchBox
                    @search_text="set_search_text"
                ></SearchBox>
            </div>

            <button>Поиск</button>

        </div>
    </div>
</template>

<script>
import CategoriesFilterComponent from '@/components/CategoriesFilterComponent.vue';
import SearchBox from '@/components/SearchBox.vue';

export default{
    props:{
        is_home_page: {
            type: Boolean,
            default: false
        }
    },
    components:{
        CategoriesFilterComponent,
        SearchBox
    },
    data(){
        return{
            search_text: ''
        }
    },
    methods:{
        set_search_text(text){
            this.search_text = text;
        }
    }
}
</script>

<style scoped>
#categiries_icon{
    width: 20px;
    height: 20px;
}
button{
    border: 0;
    background: #080210;
    border-radius: 15px;
    font-weight: 500;
    font-size: 15px;
    text-align: center;
    color: #FFFFFF;
    padding: 12px 25px;
    cursor: pointer;
}
#search_background{
    height: 23px;
    background: #FFFFFF;
    border-radius: 15px;
    display: grid;
    grid-template-columns: auto auto 1fr;
    gap: 8px;
    align-items: center;
    padding: 10px 15px;
}
#search_main{
    display: grid;
    gap: 20px;
    width: 50%;
    position: relative;
    left: 50%;
    transform: translate(-50%);
    padding: 9px;
}
</style>