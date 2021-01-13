<template>
    <div id="sidebar">
        <div class="slidein" :class="open ? 'open' : ''">
            
            <button @click="toggle">
                <img id="showLayers" :class="open ? 'rotate' : ''" src="../assets/icon/sb-open.png">
            </button>
            <div class="row">
                <div class="col-lg-12">
                    <div class="sb-iconButton my-2">
                        <img src="../assets/icon/follow.png">
                    </div>
                    <label class="sb-fontHeader h4">ช่องที่ติดตาม</label>
                </div>
            </div>

            <div class="row">
                <div class="col-lg-12">
                    <a href="#">
                        <div class="sb-img">
                            <img src="../assets/image/profile/p01.jpg">
                        </div>
                        <div class="sb-cutName h4">BabyIce Zazunggggggggggg</div>
                        <div class="sb-newVideo h6">11 วีดีโอใหม่</div>
                        <label class="sb-ststusOnline"></label>
                        <div class="sb-timeOnline">ออฟไลน์</div>
                    </a>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <a href="">
                        <div class="sb-img">
                            <img src="../assets/image/profile/p01.jpg">
                        </div>
                        <div class="sb-cutName h4">BabyIce Zazung</div>
                        <div class="sb-newVideo h6">11 วีดีโอใหม่</div>
                        <label class="sb-ststusOnline active"></label>
                        <div class="sb-timeOnline">24 นาทีออนไลน์</div>
                    </a>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <a href="">
                        <div class="sb-img active">
                            <img src="../assets/image/profile/p01.jpg">
                        </div>
                        <div class="sb-cutName h4">BabyIce Zazung</div>
                        <div class="sb-newVideo h6">11 วีดีโอใหม่</div>
                        <label class="sb-ststusOnline active"></label>
                        <div class="sb-timeOnline">24 นาทีออนไลน์</div>
                        <div class="sb-ststusLive">Live</div>
                    </a>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <a href="">
                        <div class="sb-img">
                            <img src="../assets/image/profile/p01.jpg">
                        </div>
                        <div class="sb-cutName h4">BabyIce Zazunggggggggggg</div>
                        <div class="sb-newVideo h6">11 วีดีโอใหม่</div>
                        <label class="sb-ststusOnline active"></label>
                        <div class="sb-timeOnline">24 นาทีออนไลน์</div>
                    </a>
                </div>
            </div>

            <div class="row">
                <div class="col-lg-12">
                    <div class="sb-iconButton my-2">
                        <img src="../assets/icon/video.png">
                    </div>
                    <label class="sb-fontHeader h4">ช่องที่แนะนำ</label>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <a href="">
                        <div class="sb-img">
                            <img src="../assets/image/profile/p01.jpg">
                        </div>
                        <div class="sb-cutName h4">BabyIce Zazunggggggggggg</div>
                        <div class="sb-newVideo h6">11 วีดีโอใหม่</div>
                        <label class="sb-ststusOnline"></label>
                        <div class="sb-timeOnline">ออฟไลน์</div>
                    </a>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <a href="">
                        <div class="sb-img">
                            <img src="../assets/image/profile/p01.jpg">
                        </div>
                        <div class="sb-cutName h4">BabyIce Zazunggggggggggg</div>
                        <div class="sb-newVideo h6">11 วีดีโอใหม่</div>
                        <label class="sb-ststusOnline"></label>
                        <div class="sb-timeOnline">ออฟไลน์</div>
                    </a>
                </div>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <a href="">
                        <div class="sb-img">
                            <img src="../assets/image/profile/p01.jpg">
                        </div>
                        <div class="sb-cutName h4">BabyIce Zazunggggggggggg</div>
                        <div class="sb-newVideo h6">11 วีดีโอใหม่</div>
                        <label class="sb-ststusOnline"></label>
                        <div class="sb-timeOnline">ออฟไลน์</div>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:'SideBar',
         data() {
            return {
            open: false,
            rotation: 0,
            };
        },
        
        methods: {
            toggle() {
            this.open = !this.open; 
            },
        }
    }
</script>

<style lang="css" scoped>

@media screen and (min-width: 1200px){
    .h4{font-size: 15px;}
    .h5{font-size: 13px;}
    .h6{font-size: 12px;}
    .p{font-size: 16px;}

    .slidein {
    width: 270px;
    height: 523px;
    margin: 11px 0 0 130px;
    padding: 15px 14px 21px 16px;
    object-fit: contain;
    box-shadow: -10px 3px 10px 0 rgba(0, 0, 0, 0.16);
    background-color: #24284b;
    border-radius: 8px 0 0 8px;
    position: fixed; 
    z-index: 10;
    top: 83px;
    right: -200px;
    transition: all .3s ease-in-out;
    }

    /* Set positioning back to 0 when toggled opened */
    .open {
    right: 0; 
    }

    button{
        border: none;
        background-color: #24284b;
    }

    button:focus{
        outline: none;
    }

    .sb-img img{
        width: 40px;
        height: 39px;
        margin: 5px 0 5px 15px;
        border-radius: 10px;
        border: solid 2px #ffffff;
        object-fit: cover;
        overflow: hidden;
    }

    .sb-img.active > img{
        border: solid 2px #ff0715;
    }

    .sb-fontHeader{
        font-family: 'kanitregular';
        color: #fff;
        position: absolute;
        top: 25px;
        right: 15px;
        /* left: 70px; */
    }

    .sb-iconButton{
        /* position: absolute;
        top: 10px;
        right: 15px; */
        width:46px;
        height: 47px;
        margin-left: 10px;
    }

    .sb-cutName{
        text-overflow: ellipsis;
        overflow: hidden; 
        width: 120px; 
        white-space: nowrap;
        color: #399cff;
        font-family: 'kanitmedium';
        position: absolute;
        top: 5px;
        left: 70px;
    }
    .sb-ststusOnline{
        background-color: #d82a2a;
        width: 9px;
        height: 9px;
        border-radius: 50%;
        position: absolute;
        top: 5px;
        right: 15px;
    }

    .sb-ststusOnline.active{
        background-color: #0fc680;
    }

    .sb-newVideo{
        color: #fff;
        font-family: 'kanitlight';
        position: absolute;
        top: 27px;
        left: 70px;
    }
    
    .sb-timeOnline{
        font-family: 'kanitlight';
        font-size: 9px;
        color: #fff;
        position: absolute;
        top: 27px;
        right: 15px;
    }

    .sb-ststusLive{
        font-family: 'kanitmedium';
        font-size: 10px;
        color: #fff;
        position: absolute;
        top: 35px;
        left: 21px;
        background-color: #d82a2a;
        padding: 0 5px;
        border-radius: 4px;
    }

    #showLayers {
        transition: transform 0.5s;
    }

    .rotate {
        -webkit-transform: rotate(-180deg);
        -moz-transform: rotate(-180deg);
        -o-transform: rotate(-180deg);
        -ms-transform: rotate(-180deg);
        transform: rotate(-180deg);
    }
}



</style>