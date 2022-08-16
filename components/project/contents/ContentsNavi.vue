<template>
    <div id="contents-side-navigation">
        <IconNaviItem href="/contents" icons_name="image" text="Overview" />
        <IconNaviItem href="/contents" icons_name="photo_library" text="Artworks" />
        <IconNaviItem href="/contents/artwork/posted_in" icons_name="photo_library" text="Add Artwork" />
    </div>
</template>

<style>
#contents-side-navigation {
    width: 100%;
}
</style>

<script>
import IconNaviItem from '../../navigation/IconNaviItem.vue';
export default {
    name: "ContentsNavi",
    components: { IconNaviItem }
}
</script>