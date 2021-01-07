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
                        <div style="width:140px;" data-toggle="modal" data-target="#login">
                            <img class="iconNoti" src="../assets/icon/notification.png">
                            <button class="login">Login</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!-- Modal -->
        <div class="modal fade" id="login" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered modal-md" role="document">
                <div class="modal-content" style="background-color: #202433;color:#fff;">
                    <div class="container-fluid">
                        <div class="row">
                            <div class="col-12 text-center">
                                <img class="imgModal" src="../assets/image/logo/logo3.png">
                                <img class="imgCloseModal" src="../assets/icon/close.png" data-dismiss="modal" aria-label="Close">
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-12">
                                <div class="row ml-1">
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
                                    </ul>
                                </div>

                                <div class="tab-content">
                                    <div id="tap1" class="container tab-pane active" style="padding:0;">
                                        <div class="form-group">
                                            <label class="titleInput">อีเมล</label>
                                            <input type="email" class="inputField form-control" v-model="email" name="email" required>
                                        </div>
                                        <div class="form-group">
                                            <label class="titleInput">รหัสผ่าน</label>
                                            <input type="password" class="inputField form-control" v-model="password" name="password" required>
                                        </div>
                                        <div class="text-right">
                                            <a href="#"><p class="forgotPassword">ลืมรหัสผ่าน ?</p></a>
                                        </div>
                                        <div align="center">
                                            <div  v-if=' !checkEmail && !checkPasswordLogin'>   
                                                <button type="submit" class="btnlogin">เข้าสู่ระบบ</button>
                                            </div>

                                            <div  v-else>   
                                                <button type="submit" class="btnlogin active">เข้าสู่ระบบ</button>
                                            </div>

                                            <div class="fontOr" style="margin:0;">
                                                หรือ
                                            </div>

                                            <div class="mb-4">
                                                <button class="btnFacebook">
                                                    <img class="imgFacebook" src="../assets/icon/facebook.png">
                                                    <a>เข้าสู่ระบบด้วย เฟสบุ๊ค</a>
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                    
                                    <div id="tap2" class="container tab-pane" style="padding:0;">
                                        <div class="form-group">
                                            <label class="titleInput">อีเมล</label>
                                            <input type="email" class="inputField form-control" v-model="email" name="email" required>
                                        </div>
                                        <div class="form-group">
                                            <label class="titleInput">รหัสผ่าน</label>
                                            <input type="password" class="inputField form-control" v-model="password" name="password" required>
                                        </div>
                                        
                                        <div class="form-group">
                                            <label class="titleInput mr-2">ยืนยันรหัสผ่าน</label>
                                            <label class="error" v-if='notSamePasswords'>
                                                รหัสผ่านไม่ตรงกัน
                                            </label>
                                            <input type="password" class="inputField form-control" v-model.lazy='checkPassword' required>
                                        </div>

                                        <script type="x/template" id="date-picker-template">
                                            <div class="date-picker form-inline">
                                                <div class="form-group">
                                                <select class="form-control year" v-model="year" @change="onChangeYear">
                                                    <option value="">......</option>
                                                    <option v-for="year in years" :value="year">{{year}}</option>
                                                </select>
                                                <label>Year</label>
                                                </div>
                                                <div class="form-group">
                                                <select class="form-control mouth" v-model="month" @change="onChangeMonth">
                                                    <option value="">......</option>
                                                    <option v-for="month in months" :value="month">{{month+1}}</option>
                                                </select>
                                                <label>Mouth</label>
                                                </div>
                                                <div class="form-group">
                                                <select class="form-control day" v-model="day" @change="onChangeDay">
                                                    <option value="">......</option>
                                                    <option v-for="day in days" :value="day">{{day}}</option>
                                                </select>
                                                <label>Day</label>
                                                </div>
                                            </div>
                                            </script>

                                        <div id="date-picker-demo">
                                            <date-picker :format="format" start="1950.03.03" :default="date" end="2016.02.05" @date-change="showDate"></date-picker>
                                            Current date: {{date}}
                                        </div>

                                         <transition name="hint" appear>
                                            <div class="hints" v-if='passwordValidation.errors.length > 0 && !submitted' >
                                                <div class="titlePassword">วิธีการตั้งรหัสผ่าน</div>
                                                <div v-for='error in passwordValidation.errors' :key="error">{{error}}</div>
                                            </div>
                                        </transition>

                                        <input type="checkbox" id="agreememt" value="accept" v-model="agreements" class="mr-2">
                                        <label class="accept" for="agreememt">ยอมรับ</label>
                                        <label class="acceptDes" for="agreememt">By clicking sign up, you are indicating that you have read and acknowledge the Terms of Service and Privacy Notice.</label><br>
                                        <!-- <span>ตรวจสอบการยอมรับเงื่อนไข: {{ agreements }}</span><br> -->

                                        <button class="btnlogin mb-4" @keyup='resetPasswords' v-if='passwordsFilled && !notSamePasswords && passwordValidation.valid && !acceptAgreementFilled && !checkEmailFilled && !checkNameFilled' >
                                            สมัครสมาชิก
                                        </button>
                                        <button v-else class="btnlogin active mb-4" disabled>สมัครสมาชิก</button>
                                        
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
        }
    }

    Vue.component('date-picker', {
  template: '#date-picker-template',
  props: {
    format: {
      type: String,
      default: 'YYYYMMDD'
    },
    start: {
      type: String,
      default: '19000101'
    },
    default: {
      type: String,
      default: '19900101'
    },
    end: {
      type: String,
      default: '20201231'
    }
  },
  data: function() {
    return {
      year:  '',
      month: '',
      day: '',
      years: [],
      months: [],
      days: [],
      startDate: null,
      endDate: null
    };
  },
  computed: {
    date: {
      get: function() {
        return moment({
          year: this.year,
          month: this.month,
          day: this.day
        });
      },
      set: function(v) {
        var _d = null;
        if (moment.isMoment(v)) {
          _d = v;
        } else {
          _d = moment(v, this.format);
        }
        if(!_d.isValid()) {
          throw new Error('Not valid moment or not valid time for format: ', this.format);
        }
        this.year = _d.year();
        this.month = _d.month();
        this.day = _d.date();
        console.log('Current date: ', this.year, this.month, this.day);
      }
    }
  },
  created: function() {
    var _s = moment(this.start, this.format);
    if (!_s.isValid()) {
      throw new Error('Start date is not right, or format is not right.');
    }
    var _d = moment(this.default, this.format);
    if (!_d.isValid()) {
      throw new Error('Default date is not right, or format is not right.');
    }
    var _e = moment(this.end, this.format);
    if (!_e.isValid()) {
      throw new Error('End date is not right, or format is not right.');
    }
    if (!_s.isBefore(_e)) {
      throw new Error('Start date must before end date.');
    }
    if (!_d.isBetween(_s, _e)) {
      throw new Error('Default date must between start and end.');
    }
    this.startDate = {year: _s.year(), month: _s.month(), day: _s.date()};
    this.endDate = {year: _e.year(), month: _e.month(), day: _e.date()};
    this.date = _d;
    this.getYears();
    this.getMonths();
    this.getDays();    
  },
  methods: {
    getYears: function() {
      var _to = this.endDate.year;
      for (var _y = this.startDate.year; _y <= _to; _y++) {
        this.years.push(_y);
      }
    },
    getMonths: function() {
      this.months = [];
      if (this.year === '') return;
      var _to = 11;
      var _m = 0;
      if (this.year >= this.endDate.year) {
        _to = this.endDate.month;
      }
      if (this.year <= this.startDate.year) {
        _m = this.startDate.month;
      }
      for (; _m <= _to; _m++ ) {
        this.months.push(_m);
      }
    },
    getDays: function() {
      this.days = [];
      if (this.year === '' || this.month === '') return;
      var _to = this.date.daysInMonth();
      var _d = 1;
      if (this.year <= this.startDate.year && this.month <= this.startDate.month) {
        _d = this.startDate.day;
      }
      if (this.year >= this.endDate.year && this.month >= this.endDate.month) {
        _to = this.endDate.day;
      }
      for (; _d <= _to; _d++) {
        this.days.push(_d);
      }
    },
    onChangeYear: function() {
      this.month = '';
      this.day = '';
      this.getMonths();
      this.getDays();
      this.$dispatch('date-change', this.date);
    },
    onChangeMonth: function() {
      this.day = '';
      this.getDays();
      this.$dispatch('date-change', this.date);
    },
    onChangeDay: function() {
      this.$dispatch('date-change', this.date);
    }
  }
});

new Vue({
  el: '#date-picker-demo',
  data: {
    format: 'YYYY.MM.DD',
    date: '1991.10.01'
  },
  methods: {
    showDate: function(date) {
      this.date = date.format(this.format);
    }
  }
});
</script>

<style scoped>
 
 
 @media screen and (min-width: 1200px){
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
        font-size: 12px;
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
        font-size: 12px;
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
        font-size: 12px;
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
        color: #cca343;
        border-bottom: solid 3px #202433;
        padding: 10px 2px;
    }

    .topnav a.active{
        border-bottom: solid 3px #ffffff;
    }

    .titleInput{
        margin-left: 5px;
        font-family: 'kanitmedium';
        font-size: 13px;
        color: #ffffff;
    }

    .inputField {
        width: 100%;
        height: 35px;
        margin: 0 15.6px 0 3.5px;
        object-fit: contain;
        border-radius: 8px;
        border: solid 2px #0c0d14;
        background-color: #0c0d14;
        font-family: 'kanitmedium';
        color: #ffffff;
        font-size: 13px;
    }

    .inputField:focus {
        border: solid 2px #ffffff;
        background-color: #0c0d14;
        color: #ffffff;
    }

    .forgotPassword{
        font-family: 'kanitmedium';
        font-size: 13px;
        text-decoration: underline;
        color: #cca343;
        line-height: 0;
    }

    .btnlogin{
        width: 100%;
        height: 35px;
        border-radius: 8px;
        background-color: #ffffff;
        font-family: 'kanitmedium';
        font-size: 13px;
        line-height: 1;
        font-weight: 500;
        border: none;
        margin-top: 20px;
    }

    .btnlogin.active{
        color: #615f5f;
    }
    
    .fontOr{
        color: #ffffff;
        font-size: 12px;
        font-family: 'kanitlight';
        margin: 9px;
        line-height: 3;
    }

    .btnFacebook{
        width: 100%;
        height: 35px;
        border-radius: 8px;
        background-color: #2196f3;
        border: none;
    }

    .imgFacebook{
        width: 23.3px;
        margin-right: 10px;
    }

    .btnFacebook a{
        color: #ffffff;
        font-family: 'kanitmedium';
        font-size: 13px;
        line-height:0;
        font-weight: 500;
    }
    .error{
        font-family: 'kanitmedium';
        font-size: 13px;
        color: #d80d0d;
    }

    .titlePassword{
        font-family: 'kanitmedium';
        font-size: 13px;
        color: #ffffff;
    }

    .hints {
    color: #ffffff;
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
        padding-top: 10px;
        font-family: 'kanitmedium';
        font-size: 12px;
        line-height: 0;
        color: #ffffff;
    }

    .acceptDes{
        font-family: 'kanitlight';
        font-size: 12px;
        color: #ffffff;
        margin: 0;
    }
    
}
</style>
