<template>
    <div>
        <div id="navbar">
            <div class="row" :class="{bg_navbar: scrollPosition > 0}">
                <div class="col-lg-6">
                    <!-- <vue-page-transition name="fade-in-right">  -->
                        <router-link to="/">
                            <img class="logo1 ml-5 mt-3" src="../assets/image/logo/logo.png">
                            <img class="logo2 mt-3" src="../assets/image/logo/logo2.png">
                        </router-link>
                    <!-- </vue-page-transition> -->
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
                            <button class="numberNoti h6">100</button>
                        </div>
                        <div style="width:60px;">
                            <img class="iconNoti" src="../assets/icon/notification.png">
                            <button class="numberNoti2 h6">10</button>
                        </div>
                        <div style="width:140px;" data-toggle="modal" data-target="#login">
                            <img class="iconNoti" src="../assets/icon/notification.png">
                            <button class="login h6">Login</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!-- Modal -->
        <div class="modal fade" id="login" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered modal-md" role="document">
                <div class="modal-content">
                    <div class="container-fluid">
                        <div class="row">
                            <div class="col-12 text-center">
                                <img class="imgModal" src="../assets/image/logo/logo3.png">
                                <img class="imgCloseModal" src="../assets/icon/close.png" data-dismiss="modal" aria-label="Close">
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-12">
                                <div class="row ml-1" style="height:80px">
                                    <ul class="nav topnav">
                                        <li class="nav-item mr-4 ">
                                            <a class="nav-link active" data-toggle="tab" href="#tap1">
                                                <div>เข้าสู่ระบบ</div>
                                            </a>
                                        </li>
                                        <li class="nav-item">
                                            <a class="nav-link" data-toggle="tab" href="#tap2">
                                                <div>สมัครสมาชิก</div>
                                            </a>
                                        </li>
                                        <div class="line"></div>
                                    </ul>
                                </div>

                                <div class="tab-content">
                                    <div id="tap1" class="container tab-pane active" style="padding:0;">
                                        <div class="form-group">
                                            <label class="titleInput">อีเมลหรือเบอร์โทรศัพท์</label>
                                            <input type="email" class="inputField form-control" v-model="email" name="email" placeholder="อีเมลหรือเบอร์โทรศัพท์" required>
                                        </div>
                                        <div class="form-group">
                                            <label class="titleInput">รหัสผ่าน</label>
                                            <input type="password" class="inputField form-control" v-model="password" placeholder="รหัสผ่าน" name="password" required>
                                        </div>
                                        <div class="text-right">
                                            <a href="#"><p class="forgotPassword">ลืมรหัสผ่าน ?</p></a>
                                        </div>
                                        <div align="center">
                                            <div  v-if=' !checkEmail && !checkPasswordLogin'>   
                                                <button type="submit" class="btnlogin mt-3">เข้าสู่ระบบ</button>
                                            </div>

                                            <div  v-else>   
                                                <button type="submit" class="btnlogin btnloginDis mt-3" disabled>เข้าสู่ระบบ</button>
                                            </div>

                                            <div class="mb-4">
                                                <button class="btnFacebook">
                                                    <img class="imgFacebook" src="../assets/icon/facebook.png">
                                                    <a>Log In with Facebook</a>
                                                </button>
                                                <button class="btnGoogle">
                                                    <img class="imgFacebook" src="../assets/icon/google.png">
                                                    <a>Log In with Google</a>
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                    
                                    <div id="tap2" class="container tab-pane" style="padding:0;">
                                        <div class="form-group">
                                            <label class="titleInput">อีเมลหรือเบอร์โทรศัพท์</label>
                                            <input type="email" class="inputField form-control" v-model="email" name="email" placeholder="อีเมลหรือเบอร์โทรศัพท์" required>
                                        </div>
                                        <div class="form-group">
                                            <label class="titleInput">รหัสผ่าน</label>
                                            <input type="password" class="inputField form-control" v-model="password" name="password" placeholder="รหัสผ่าน" required>
                                        </div>
                                        
                                        <div class="form-group">
                                            <label class="titleInput mr-2">ยืนยันรหัสผ่าน</label>
                                            <label class="error" v-if='notSamePasswords'>
                                                รหัสผ่านไม่ตรงกัน
                                            </label>
                                            <input type="password" class="inputField form-control" v-model.lazy='checkPassword' placeholder="ยืนยันรหัสผ่าน" required>
                                        </div>

                                        <div>
                                            <label class="titleInput mr-2">วัน/เดือน/ปี เกิด</label><br>
                                            <BirthDatepicker />
                                        </div>

                                         <transition name="hint" appear>
                                            <div class="hints" v-if='passwordValidation.errors.length > 0 && !submitted' >
                                                <div class="titlePassword">วิธีการตั้งรหัสผ่าน</div>
                                                <div v-for='error in passwordValidation.errors' :key="error">{{error}}</div>
                                            </div>
                                        </transition>

                                        <input type="checkbox" id="agreememt" value="accept" v-model="agreements" class="mr-2 mt-2">
                                        <label class="accept" for="agreememt">ยอมรับ By clicking sign up, you are indicating that you have read and acknowledge the Terms of Service and Privacy Notice.</label>
                                        <label class="acceptDes" for="agreememt"></label><br>
                                        <!-- <span>ตรวจสอบการยอมรับเงื่อนไข: {{ agreements }}</span><br> -->

                                        <div @keyup='resetPasswords' v-if='passwordsFilled && !notSamePasswords && passwordValidation.valid && !acceptAgreementFilled && !checkEmailFilled && !checkNameFilled'>
                                            <button class="btnlogin mt-2 mb-4" >
                                                สมัครสมาชิก
                                            </button>
                                        </div>
                                        <div v-else>
                                            <button class="btnlogin btnloginDis mt-2 mb-4" disabled>สมัครสมาชิก</button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Vue from 'vue'
import vuescroll from 'vue-scroll'
import VuePageTransition from 'vue-page-transition'
import BirthDatepicker from 'vue-birth-datepicker';
 
Vue.use(VuePageTransition)
Vue.use(vuescroll)
    export default {
        name: "Navbar",
        data(){
            return{
                scrollPosition: null,
                email:'',
                password:'',
                checkPassword:'',
                passwordVisible:false,
                submitted:false,
                agreements: [],
                rules: [
                    { message:"ตัวอักษรพิมพ์เล็กอย่างน้อย 1 ตัว", regex:/[a-z]+/ },
                    { message:"ตัวอักษรพิมพ์เล็กอย่างใหญ่ 1 ตัว",  regex:/[A-Z]+/ },
                    { message:"ต้องมีอย่างน้อย 8 ตัวอักษร", regex:/.{8,}/ },
                    { message:"ตัวเลข อย่างน้อย 1 ตัว", regex:/[0-9]+/ }
                ],
            }
        },
        methods: {
            updateScroll() {
            this.scrollPosition = window.scrollY
            },
            resetPasswords () {
                this.email =''
                this.name=''
                this.password = ''
                this.checkPassword = ''
                this.submitted = true
                setTimeout(() => {
                    this.submitted = false
                }, 2000)
            }
        },
        mounted() {
            window.addEventListener('scroll', this.updateScroll);
        },
        computed:{
            checkEmail(){
                return(this.email == '')
            },
            checkPasswordLogin(){
                return(this.password =='')
            },
            notSamePasswords () {
                if (this.passwordsFilled) {
                    return (this.password !== this.checkPassword)
                } else {
                    return false
                }
            },
            passwordsFilled () {
                return (this.password !== '' && this.checkPassword !== '')
            },
            passwordValidation () {
                let errors = []
                for (let condition of this.rules) {
                    if (!condition.regex.test(this.password)) {
                        errors.push(condition.message)
                    }
                }
                if (errors.length === 0) {
                    return { valid:true, errors }
                } else {
                    return { valid:false, errors }
                }
            },
            acceptAgreementFilled(){
                return (this.agreements == '')
            },
            checkEmailFilled(){
                return(this.email == '')
            }
        },
        components:{
            BirthDatepicker
        }
    }
</script>

<style scoped>
 
 @media screen and (min-width: 1200px){
    .h4{font-size: 18px;}
    .h5{font-size: 13px;}
    .h6{font-size: 12px;}
    .p{font-size: 16px;}
     
     #navbar{
        position: fixed;
        width: 100%;
        z-index: 10;
    }

    .bg_navbar{
        -webkit-transition: background-color 1s ease-out;
        -moz-transition: background-color 1s ease-out;
        -o-transition: background-color 1s ease-out;
        transition: background-color 1s ease-out;
        background-color: #141621;
        height: 80px;
        box-shadow: 0 3px 6px 0 rgba(0, 0, 0, 0.42);

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
        cursor: pointer;
    }

    .numberNoti{
        font-family: 'kanitregular';
        color: #fff;
        background-color:#d50915;
        border-radius: 25px;
        border: none;
        line-height: 1;
        padding-bottom: 2px;
        position: relative;
        /* z-index: 12; */
        top: -55px;
        left: 45px;
    }

    .iconNoti{
        width: 52px;
        height: 54px;
        margin: 12px 0 0 0;
        cursor: pointer;
    }
    .numberNoti2{
        font-family: 'kanitregular';
        color: #fff;
        background-color:#d50915;
        border-radius: 25px;
        border: none;
        line-height: 1;
        padding-bottom: 2px;
        position: relative;
        /* z-index: 12; */
        top: -55px;
        left: 40px;
    }

    .login{
        font-family: 'kanitregular';
        color: #fff;
        background-color:#399cff;
        border-radius: 7px 7px 7px 0;
        border: none;
        position: relative;
        /* z-index: 15; */
        top: -10px;
        left: -15px;
    }

    .login{
        outline: none;
    }

    /* Modal */
    .imgModal{
        width: 174px;
        height: 42px;
        margin-top: 18px;
    }

    .imgCloseModal{
        position: absolute;
        top: 35px;
        right: 20px;
        cursor: pointer;
    }

    .topnav{
        height: 90px;
    }

    .topnav a{
        margin-top: 32px;
        font-family: 'kanitmedium';
        font-size: 13px;
        color: #989898;
        border-bottom: solid 4px #fff;
        padding:15px 0 ;
        line-height: 0;
    }

    .topnav a.active{
        border-bottom: solid 3px #2d3359;
        color:#2d3359;
        z-index: 1;
    }

    /* .topnav a::after {
        margin-top: 18px;
        content: '';
        display: block;
        width: 0;
        height: 4px;
        background: #2d3359;
        transition: width .3s;
        z-index: 0;
    }

    .topnav a:hover::after {
        width: 100%;
    } */

    .line{
        width:94%;
        height: 1px;
        opacity: 0.3;
        background-color: #707070;
        position: absolute;
        top: 63px;
        left: 18px;
        z-index: 0;
    }

    .titleInput{
        margin-left: 5px;
        font-family: 'kanitmedium';
        font-size: 13px;
        color: #989898;
    }

    .inputField {
        width: 100%;
        height: 46px;
        margin: 0 15.6px 0 0;
        object-fit: contain;
        border-radius: 6px;
        border: solid 1px #989898;
        background-color: #e3e3e3;
        font-family: 'kanitmedium';
        color: #5a5f83;
        font-size: 13px;
    }

    .inputField::placeholder{
     color:#5a5f83;
    } 
    .inputField:focus {
        border: solid 1px #989898;
        background-color: #e3e3e3;
        color: #5a5f83;
        /* outline: none; */
        box-shadow: none;
    }

    .forgotPassword{
        font-family: 'kanitmedium';
        font-size: 13px;
        text-decoration: underline;
        color: #cca343;
        line-height: 0;
    }

    .btnlogin{
        font-family: 'kanitmedium';
        font-size: 13px;
        color: #fff;
        height: 46px;
        width: 100%;
        border-radius: 12px;
        box-shadow: 0 10px 15px 0 rgba(26, 64, 149, 0.25);
        border: solid 2px #4e7bf7;
        background-color: #4e7bf7;
    }

    .btnloginDis{
        opacity: 0.5;
    }
    

    .btnFacebook{
        width: 100%;
        height: 46px;
        margin: 13px 5.5px 13px 0;
        padding: 8px 77.7px 14.3px 61.4px;
        border-radius: 12px;
        box-shadow: 0 10px 15px 0 rgba(26, 64, 149, 0.25);
        border: solid 1px #4e7bf7;
        background-color: #ffffff;
    }

    .btnFacebook a{
        color: #4076ff;
        font-family: 'kanitregular';
        margin-left: 10px;
        font-size: 13px;
        line-height:0;
        font-weight: 500;
        text-decoration: none;
    }

    .imgFacebook{
        width: 23.3px;
        margin-right: 10px;
    }

    .btnGoogle{
        width: 100%;
        height: 46px;
        margin: 0 5.5px 13px 0;
        padding: 8px 77.7px 14.3px 61.4px;
        border-radius: 12px;
        box-shadow: 0 10px 15px 0 rgba(173, 22, 22, 0.25);
        border: solid 1px#f24250;
        background-color: #ffffff;
    }

    .btnGoogle a{
        color: #f5404b;
        font-family: 'kanitregular';
        margin-left: 10px;
        font-size: 13px;
        line-height:0;
        font-weight: 500;
        text-decoration: none;
    }



    .error{
        font-family: 'kanitmedium';
        font-size: 13px;
        color: #d80d0d;
    }

    .titlePassword{
        font-family: 'kanitmedium';
        font-size: 13px;
        color:#989898;
    }

    .hints {
    color: #989898;
    font-size: 12px;
    font-family: 'kanitlight';
    margin-left: 5px;
    }

    input:focus{
        outline: none;
    }

    button:focus{
        outline: none;
    }
    
    .accept{
        vertical-align: text-top;
        padding-top: 3px;
        font-family: 'kanitmedium';
        font-size: 12px;
        line-height: 1.2;
        color: #989898;
        width: 90%;
    }

    .acceptDes{
        font-family: 'kanitlight';
        font-size: 12px;
        color: #989898;
        margin: 0;
    }
}
</style>
