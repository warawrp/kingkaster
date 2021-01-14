<template>
    <div id="sidebar">
        <div class="slidein" :class="open ? 'open' : ''">
            
            <button @click="toggle">
                <img id="showLayers" :class="open ? 'rotate' : ''" src="../assets/icon/sb-open.png">
            </button>
            <div class="row">
                <div class="col-lg-12">
                    <div class="sb-iconButton">
                        <img src="../assets/icon/follow.png">
                    </div>
                    <label class="sb-fontHeader h4">ช่องที่ติดตาม</label>
                </div>
            </div>

            <div class="row " v-for="follow in follows" :key="follow.id">
                <div class="col-lg-12">
                    <a href="#">
                        <div v-if="follow.live == 1">
                            <div class="sb-img active">
                                <img :src="follow.image">
                            </div>
                            <div class="sb-ststusLive">Live</div>
                        </div>

                        <div v-else>
                            <div class="sb-img">
                                <img :src="follow.image">
                            </div>
                        </div>
                        
                        <div class="sb-cutName h4">{{follow.name}}</div>
                        <div class="sb-newVideo h6">{{follow.video}} วีดีโอใหม่</div>
                        <label class="sb-ststusOnline" v-if="follow.status != 1"></label>
                        <label class="sb-ststusOnline active" v-else></label>
                        <div class="sb-timeOnline">{{follow.timeOnline}}</div>
                    </a>
                </div>
            </div>
            

            <div class="row">
                <div class="col-lg-12">
                    <div class="sb-iconButton">
                        <img src="../assets/icon/video.png">
                    </div>
                    <label class="sb-fontHeader h4">ช่องที่แนะนำ</label>
                </div>
            </div>
            <div class="row " v-for="recommend in recommends" :key="recommend.id">
                <div class="col-lg-12">
                    <a href="#">
                        <div v-if="recommend.live == 1">
                            <div class="sb-img active">
                                <img :src="recommend.image">
                            </div>
                            <div class="sb-ststusLive">Live</div>
                        </div>

                        <div v-else>
                            <div class="sb-img">
                                <img :src="recommend.image">
                            </div>
                        </div>
                        
                        <div class="sb-cutName h4">{{recommend.name}}</div>
                        <div class="sb-newVideo h6">{{recommend.video}} วีดีโอใหม่</div>
                        <label class="sb-ststusOnline" v-if="recommend.status != 1"></label>
                        <label class="sb-ststusOnline active" v-else></label>
                        <div class="sb-timeOnline">{{recommend.timeOnline}}</div>
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
                follows:[
                    {
                        id: '1',
                        image:'https://cdn.pixabay.com/photo/2021/01/04/12/44/cat-5887426__340.jpg',
                        name: 'BabyIce Zazunggggggggggg',
                        video: '5',
                        status: '1',
                        timeOnline: '21 นาทีออนไลน์',
                        live:'1'
                    },
                    {
                        id: '2',
                        image:'https://cdn.pixabay.com/photo/2020/12/25/09/46/dog-5858985__340.jpg',
                        name: 'BabyIce Zazunggggggggggg',
                        video: '3',
                        status: '0',
                        timeOnline: 'ออฟไลน์',
                        live:'0'
                    },
                    {
                        id: '3',
                        image:'https://cdn.pixabay.com/photo/2020/12/16/10/44/cat-5836297__340.jpg',
                        name: 'BabyIce Zazunggggggggggg',
                        video: '9',
                        status: '1',
                        timeOnline: '10 นาทีออนไลน์',
                        live:'0'
                    },
                    {
                        id: '4',
                        image:'https://cdn.pixabay.com/photo/2020/09/19/20/01/woman-5585332__340.jpg',
                        name: 'BabyIce Zazunggggggggggg',
                        video: '5',
                        status: '1',
                        timeOnline: '30 นาทีออนไลน์',
                        live:'0'
                    }
                ],
                recommends:[
                    {
                        id: '1',
                        image:'https://cdn.pixabay.com/photo/2019/05/21/07/11/cat-4218424__340.jpg',
                        name: 'BabyIce Zazunggggggggggg',
                        video: '8',
                        status: '0',
                        timeOnline: 'ออฟไลน์',
                        live:'0'
                    },
                    {
                        id: '2',
                        image:'https://cdn.pixabay.com/photo/2020/07/30/10/29/woman-5450043__340.jpg',
                        name: 'BabyIce Zazunggggggggggg',
                        video: '2',
                        status: '1',
                        timeOnline: '8 นาทีออนไลน์',
                        live:'1'
                    },
                    {
                        id: '3',
                        image:'https://cdn.pixabay.com/photo/2019/10/28/21/21/halloween-4585684__340.jpg',
                        name: 'BabyIce Zazunggggggggggg',
                        video: '1',
                        status: '0',
                        timeOnline: 'ออฟไลน์',
                        live:'0'
                    }
                ]
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
    margin: 11px 0 0 130px;
    padding: 15px 14px 10px 16px;
    object-fit: contain;
    box-shadow: -10px 3px 10px 0 rgba(0, 0, 0, 0.16);
    background-color: #24284b;
    border-radius: 8px 0 0 8px;
    position: fixed; 
    z-index: 10;
    top: 75px;
    right: -205px;
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
        width: 35px;
        height: 35px;
        margin: 7px 0 0 15px;
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
        margin: 10px 0 0 15px;
    }

    .sb-iconButton > img{
        width: 35px;
    }

    .sb-cutName{
        text-overflow: ellipsis;
        overflow: hidden; 
        width: 120px; 
        white-space: nowrap;
        color: #399cff;
        font-family: 'kanitmedium';
        position: absolute;
        top: 8px;
        left: 65px;
    }
    .sb-ststusOnline{
        background-color: #d82a2a;
        width: 9px;
        height: 9px;
        border-radius: 50%;
        position: absolute;
        top: 15px;
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
        left: 65px;
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
        top: 30px;
        left: 18px;
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

@media screen and (min-width: 1300px){

    .sb-img img{
        width: 40px;
        height: 40px;
        margin: 6px 0 3px 12px;
        border-radius: 10px;
        border: solid 2px #ffffff;
        object-fit: cover;
        overflow: hidden;
    }

    .sb-img.active > img{
        border: solid 2px #ff0715;
    }

    .sb-ststusLive{
        font-family: 'kanitmedium';
        font-size: 10px;
        color: #fff;
        position: absolute;
        top: 35px;
        left: 18px;
        background-color: #d82a2a;
        padding: 0 5px;
        border-radius: 4px;
    }

    .sb-iconButton{
        margin: 10px 0 0 12px;
    }

    .sb-iconButton > img{
        width: 40px;
    }
}



</style>