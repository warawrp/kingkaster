<template>
    <div id="navbar" class="container-fluid">
        <div class="row" :class="{bg_navbar: scrollPosition > 0}">
            <div class="col-lg-6">
                <vue-page-transition name="fade-in-right"> 
                    <router-link to="/">
                        <img class="logo1 ml-5 mt-3" src="../assets/image/logo.png" alt="">
                        <img class="logo2 mt-3" src="../assets/image/logo2.png" alt="">
                    </router-link>
                </vue-page-transition>
            </div>
            <div class="col-lg-6 ">
                <div class="row d-flex justify-content-end">
                    <div style="width:401px;">
                        <img class="iconSearch" src="../assets/icon/search.png">
                        <input type="text" class="inputSearch" placeholder="ค้นหาข้อความ">
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
import VuePageTransition from 'vue-page-transition'
 
Vue.use(VuePageTransition)
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
 
 
 @media screen and (min-width: 1200px){
    h4{
        font-size: 18px;
    }

    h5{
        font-size: 13px;
    }

    p{
        font-size: 16px;
    }

    .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6,
    .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12{
        padding:0 !important;
    }

    #navbar{
        position: fixed;
        top: 0;
        left: 0;
        z-index: 10;
    }

    .bg_navbar{
        -webkit-transition: background-color 1s ease-out;
        -moz-transition: background-color 1s ease-out;
        -o-transition: background-color 1s ease-out;
        transition: background-color 1s ease-out;
        background-color: #141621;
        height: 80px;
    }

    .logo1{
        height: 49px;
    }
    .logo2{
        height: 18px;
    }
    
    .inputSearch{
        font-family: 'kanitlight';
        font-size: 16px;
        color:#fff;
        width: 401px;
        height: 43px;
        margin-top: -5px;
        padding: 0 0 0 45px;
        background-color: rgba(255, 255, 255, 0.342);
        border-radius: 7px;
        border: solid 1px #ffffff;
    }

    .inputSearch:focus{
        outline: none;
    }

    .inputSearch::placeholder{
     color:#fff;
    }  

    .btn-search{
        font-family: 'kanitregular';
        color: #fff;
        width: 89px;
        height: 43px;
        position: relative;
        top:-43px;
        left:313px;
        border-radius: 7px;
        border: solid 1px #ffffff;
        background-color: #399cff;
    }

    .btn-search:focus{
        outline: none;
    }

    .iconSearch{
        position: relative;
        width: 17.9px;
        height: 18.4px;
        top: 25px;
        left: 15px;
    }
    .iconCart{
        width: 52px;
        height: 54px;
        margin: 12px 0 0 10px;
    }

    .numberNoti{
        font-family: 'kanitregular';
        font-size: 12px;
        color: #fff;
        background-color:#d50915;
        border-radius: 25px;
        border: none;
        line-height: 1;
        padding-bottom: 2px;
        position: relative;
        z-index: 12;
        top: -55px;
        left: 45px;
    }

    .numberNoti:focus{
        outline: none;
    }

    .iconNoti{
        width: 52px;
        height: 54px;
        margin: 12px 0 0 0;
    }
    .numberNoti2{
        font-family: 'kanitregular';
        font-size: 12px;
        color: #fff;
        background-color:#d50915;
        border-radius: 25px;
        border: none;
        line-height: 1;
        padding-bottom: 2px;
        position: relative;
        z-index: 12;
        top: -55px;
        left: 40px;
    }

    .numberNoti2:focus{
        outline: none;
    }

    .login{
        font-family: 'kanitregular';
        font-size: 12px;
        color: #fff;
        background-color:#399cff;
        border-radius: 7px 7px 7px 0;
        border: none;
        position: relative;
        z-index: 15;
        top: -10px;
        left: -15px;
    }

    .login{
        outline: none;
    }

}
</style>
