<template>
    <div>
        <div id="authorization_main"
            v-if="$store.state.user"
        >
            <img src="@/assets/png_icons/user.png" alt="User icon">
            <p>Войти</p>
        </div>

        <div id="main"
            v-if="!$store.state.user"
        >
            <p>Ваш профиль</p>
            <img src="@/assets/svg_icons/burger.svg" alt="Burger icon">
        </div>
    </div>
</template>

<script>
export default{

}
</script>

<style scoped>
#main{
    display: flex;
    gap: 10px;
}
#authorization_main{
    display: flex;
    gap: 5px;
}
img{
    width: 20px;
    height: 20px;
}
p{
    font-weight: 500;
    font-size: 12px;
    color: #000000;
    white-space: nowrap;
}
</style>