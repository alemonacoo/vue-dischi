<template>
<header>
    <img src="@/assets/logo.png" alt="spotify logo">
</header>
</template>

<script>
export default {
    name: "HeaderComponent"
}
</script>

<style lang="scss" scoped>
@import '@/assets/main.scss';
header{
    height: 7vh;
    width: 100%;
    background-color: $app-light;
    img{
        padding: 5px;
        height: 100%;
    }
}


</style>