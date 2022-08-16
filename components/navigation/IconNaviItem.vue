<template>
    <a :href="href" class="icon-navi-item">
        <p class="material-icons">{{ icons_name }}</p>
        <p class="text">{{ text }}</p>
    </a>
</template>

<style>
.icon-navi-item {
    height: 50px;
    line-height: 50px;
    display: flex;
    padding: 0 12px;
}
.icon-navi-item .text {
    margin-left: 10px;
    font-size: 13px;
    font-weight: bold;
}
.icon-navi-item .material-icons {
    width: 25px;
    height: 25px;
    font-size: 25px;
    margin: 11px 0;
}
</style>

<script>
export default {
    name: "IconNaviItem",
    props: ['href', 'icons_name', 'text']
}
</script>