<template>
    <div id="dashbord-main">
        <div id="side-panel">
            <a href="/" class="navi-item overview"></a>
            <a href="/" class="navi-item notification"></a>
            <a href="/" class="navi-item inbox"></a>
        </div>
        <div id="side-actions">
            <a href="/" class="action-menu">収益化</a>
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
    display: flex;
}
#side-panel {
    width: 66px;
    height: 100vh;
    padding: 12px 6px;
    background-color: #292F4C;
}
#side-panel .navi-item {
    display: block;
    cursor: pointer;
    width: 25px;
    height: 25px;
    margin: 0 auto 20px auto;
}
#side-panel .navi-item::before {
    font-family: 'Material Icons';
    display: block;
    font-size: 25px;
    color: #ffffff;
}
#side-panel .navi-item.overview::before {
    content: '\e871';
}
#side-panel .navi-item.notification::before {
    content: '\e7f4';
}
#side-panel .navi-item.inbox::before {
    content: '\e156';
}

#side-actions {
    width: 256px;
    height: 100vh;
    background-color: #F6F7FB;
}
#side-actions .action-menu {
    display: block;
    width: 100%;
    height: 45px;
    line-height: 45px;
    padding: 0 12px;
}

#main-panel {
    padding: 20px;
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
