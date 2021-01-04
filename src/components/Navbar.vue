<template>
    <div id="navbar" class="container-fluid">
        <div class="row" :class="{bg_navbar: scrollPosition > 0}">
            <div class="col-lg-6">
                <router-link to="/">
                    <img class="logo1 ml-5 mt-3" src="../assets/image/logo.png" alt="">
                    <img class="logo2 mt-3" src="../assets/image/logo2.png" alt="">
                </router-link>
            </div>
            <div class="col-lg-6 ">
                <div class="row d-flex justify-content-end">
                    <div style="width:401px;">
                        <img class="iconSearch" src="../assets/icon/search.png">
                        <input type="text" class="inputSearch p" placeholder="ค้นหาข้อความ">
                        <button class="btn-search p " type="button">ค้นหา</button>
                    </div>
                    <div style="width:70px;">
                        <img class="iconCart" src="../assets/icon/cart.png">
                        <button class="numberNoti">100</button>
                    </div>
                    <div style="width:60px;">
                        <img class="iconNoti" src="../assets/icon/notification.png">
                        <button class="numberNoti2">10</button>
                    </div>
                    <div style="width:100px;">
                        <img class="iconNoti" src="../assets/icon/notification.png">
                        <button class="login">Login</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- <nav >
            <ul >
                <li>
                    <router-link to="/">
                        <img class="logo ml-5 mt-3" src="../assets/image/logo.png" alt="">
                        <img class="logo2 mt-3" src="../assets/image/logo2.png" alt="">
                    </router-link>
                </li>
            </ul>
        </nav> -->
    </div>
</template>

<script>
import Vue from 'vue'
import vuescroll from 'vue-scroll'
 
Vue.use(vuescroll)
    export default {
        name: "Navbar",
        data(){
            return{
                scrollPosition: null
            }
        },
        methods: {
            updateScroll() {
            this.scrollPosition = window.scrollY
            }
        },
        mounted() {
            window.addEventListener('scroll', this.updateScroll);
        }
    }
</script>

<style scoped>
 .col-lg-6{
     color:#fff;
 }
 ::placeholder{
     color:#fff;
 }
</style>
