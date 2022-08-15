<template>
    <div id="dashbord-main">
        <div id="side-panel">

            <a href="/" class="navi-item overview active">
                Overview
            </a>
            <a href="#" class="navi-item activity">
                Activity
            </a>
        </div>
        <div id="main-panel">
            <nuxt />
        </div>
    </div>
</template>

<style>
* {
    margin: 0;
    padding: 0;
    text-decoration: none;
    box-sizing: border-box;
    color: #000000;
}
#dashbord-main {
    width: 100%;
    height: 100vh;
    overflow: hidden;
}
#side-panel {
    width: 250px;
    height: 100vh;
    overflow-y: auto;
    padding: 24px;
    border-right: 1px solid #ccc;
}
#side-panel .navi-item {
    font-family: 'Roboto', sans-serif;
    width: 100%;
    height: 45px;
    display: block;
    line-height: 45px;
    position: relative;
    padding-left: 40px;
    font-size: 13px;
    font-weight: bold;
    cursor: pointer;
    color: #707070;
}
#side-panel .navi-item::before {
    font-family: 'Material Icons';
    display: block;
    position: absolute;
    top: -1px;
    left: 6px;
    font-size: 25px;
}
#side-panel .navi-item.overview::before {
    content: '\e871';
}
#side-panel .navi-item.activity::before {
    content: '\eaa2';
}
#side-panel .navi-item.active {
    color: #b08ff3;
}
</style>

<script>
export default {
  name: 'DefaultLayout',
  head: {
    link: [
        { href: 'https://fonts.googleapis.com/icon?family=Material+Icons', rel: 'stylesheet' },
        { href: 'https://fonts.googleapis.com', rel: 'preconnect' },
        { href: 'https://fonts.gstatic.com', rel: 'preconnect' },
        { href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap', rel: 'stylesheet' },
    ]
  }
}
</script>
