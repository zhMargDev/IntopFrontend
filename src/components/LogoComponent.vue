<template>
    <div id="logoBox">
        <img src="@/assets/logo/logo.svg" alt="Logotype">
        <h3 readonly >INT<span>O</span>P</h3>
    </div>
</template>


<style scoped>
img{
    height: 27px;
    margin-right: 10.5px;
}
span{
    color: #f16a26 !important;
}
h3, span{
    font-family: 'Russo One';
    font-weight: bold;
    font-size: 22px;
    line-height: 27px;
    letter-spacing: 0.09em;
    color: #000000;
    -webkit-user-select: none; /* Safari */
    -moz-user-select: none; /* Firefox */
    -ms-user-select: none; /* IE10+/Edge */
    user-select: none; /* Standard */
    transition: 300ms;
}
#logoBox{
    display: flex;
    align-items: center;
    cursor: pointer;
}
</style>