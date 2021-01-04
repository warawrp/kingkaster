<template>
    <div id="navbar">
        <div class="bg-navbar">
            <router-link to="/">
            <img class="logo ml-5 mt-3" src="../assets/image/logo.png" alt="">
            <img class="logo2 mt-3" src="../assets/image/logo2.png" alt="">
            </router-link>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Navbar",
    }
</script>
<style lang="css">
    #navbar{
        position: absolute;
        top: 0;
        left: 0;
        z-index: 10;
    }

    
</style>
