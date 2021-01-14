<template>
    <div id="livevideo">
       <div class="row mb-5" style="width:100%; padding-left:15px;">
            <div class="col-lg-12">
                <div class="row" style="padding-left:10px;">
                    <div class="col-lg-6">
                        <label class="rc-fontHeader h2 mr-3">Live ล่าสุด</label>
                        <a href="#">
                            <label class="it-fontMore h2 mr-2">More</label>
                            <div class="arrowMore"><img src="../assets/icon/arrowMore.png"></div>
                        </a>
                    </div>
                </div>
                <div class="row" style="width:100%;padding-left:10px;">
                    <div class="col-lg-12">
                        <div class="row" style="padding: 0 50px 0 80px">
                            
                            <div class="col-lg-5 lv-bg">
                                <a href="#">
                                    <img class="lv-video" src="https://cdn.pixabay.com/photo/2020/03/01/00/55/compass-4891499__340.jpg">
                                    <div class="lv-bth h6">ผู้เข้าชม : 123K
                                        <img class="lv-btnImg" src="../assets/icon/facebook.png">
                                    </div>
                                    <img class="lv-imgProfile active" src="https://cdn.pixabay.com/photo/2019/10/29/10/07/man-4586576__340.jpg">
                                    <div class="lv-btnLive h3">Live</div>
                                    <div style="margin-bottom:0;" class="lv-videoName h3">WE HIT 1,800 FOLLOWERS BOISssssssssssssssssssss</div>
                                    <div class="lv-casterName h3">TheSquash</div>
                                </a>
                            </div>
                            <div class="col-lg-7">
                                
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    // import carousel from 'vue-owl-carousel'
    export default {
        name:'LiveVideo',
        // components: { carousel },
        data(){
            return{
            }
        }
    }
</script>

<style lang="css" scoped>
    @media screen and (min-width: 1200px){
        .h1{font-size: 23px;}
        .h2{font-size: 22px;}
        .h3{font-size: 19px;}
        .h4{font-size: 18px;}
        .h5{font-size: 13px;}
        .h6{font-size: 12px;}
        .p{font-size: 16px;}

        .arrowMore{
            position: absolute;
            top: 28px;
            left: 235px;
        }

        .slick-wrapper {
            width: 80%;
            background-color: aqua;
        }
        .slide-item {
            background-color: rebeccapurple;
            color: aqua;
            display: flex !important;
            justify-content: center;
            align-items: center;
            text-align: center;
            height: 200px;
            border: 1px solid white;
        }

    }
</style>