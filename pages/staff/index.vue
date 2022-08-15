<template>
  <div id="staff-view">
    <h1>スタッフリスト</h1>
    <div id="staff-list">
        <div class="staff-card">
            <div class="staff-icon">
                <img src="https://www.appbank.net/wp-content/uploads/2022/03/IMG_8412.jpeg" alt="">
            </div>
            <div class="profile">
                <h3>テトラポッド</h3>
                <p class="subtitle">tetrapod@glow.com</p>
            </div>
            <div id="signin-btn">
                ログイン
            </div>
        </div>
        <div class="staff-card">
            <div class="staff-icon">
                <img src="https://www.appbank.net/wp-content/uploads/2022/03/IMG_8412.jpeg" alt="">
            </div>
            <div class="profile">
                <h3>テトラポッド</h3>
                <p class="subtitle">tetrapod@glow.com</p>
            </div>
            <div id="signin-btn">
                ログイン
            </div>
        </div>
    </div>
  </div>
</template>

<style>
#main-panel {
    width: 100%;
    background-color: #f1ece7;
}
#staff-view h1 {
    margin-bottom: 70px;
}
#staff-list {
    display: flex;
}
.staff-card {
    width: 270px;
    border-radius: 8px;
    position: relative;
    text-align: center;
    background-color: #ffffff;
    padding-top: 60px;

    margin-right: 20px;
}
.staff-card .profile .subtitle {
    color: #cccccc;
    font-size: 13px;
    line-height: 2em;
}
.staff-card .staff-icon {
    width: 78px;
    height: 78px;
    border-radius: 50%;
    overflow: hidden;
    margin: 0 auto;
    position: absolute;
    top: -40px;
    left: 95px;
}
.staff-card .staff-icon img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

#signin-btn {
    margin-top: 20px;
    background-color: #000000;
    color: #ffffff;
    padding: 12px 0;
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
}
</style>

<script>
export default {
    name: "StaffPage",
    layout: "default",
    mounted() {
        this.setNavigation();
    },
    methods: {
        setNavigation() {
            this.$nuxt.$emit('setNavigation', 'staff');
        }
    }
}
</script>
