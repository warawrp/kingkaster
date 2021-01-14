<template>
    <div id="Recommend">
        <div class="row">
            <div class="col-lg-12 bg-rc">
                <div class="row" style="width:100%; padding-left:15px;">
                    <div class="col-lg-12">
                        <label class="rc-fontHeader h2">ช่องที่แนะนำ</label>
                        <div style="padding: 0 50px 0 60px">
                            <carousel 
                                :autoplay="false" 
                                :loop="false" 
                                :nav="false"
                                :dots="false"
                                :responsive="{0:{items:1,nav:false},600:{items:3,nav:false},1200:{items:4,nav:false},1900:{items:5,nav:false}}"
                                @changed="changed" @updated="updated">
                                <div style="padding:0 30px 0 10px">
                                    <div class="row" style="padding-left:7px">
                                        <div class="col-lg-12 mb-2">
                                            <img width="100%" src="../assets/image/logo/gaming.png">
                                            <div class="rc-header h1">Game</div>
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col-lg-6" v-for="game in games" :key="game.id">
                                            <a href="#">
                                                <div style="padding: 4px 1.5px 2px 0">
                                                    <img class="rc-img" :src="game.image">
                                                    <div class="rc-coverImg"></div>
                                                    <div class="rc-name h5">{{game.name}}</div>
                                                    <label class="rc-ststusOnline" v-if="game.status != 1"></label>
                                                    <label class="rc-ststusOnline active" v-else></label>
                                                </div>
                                            </a>
                                        </div>
                                    </div>
                                </div>

                                <div style="padding:0 30px 0 10px">
                                    <div class="row" style="padding-left:7px">
                                        <div class="col-lg-12 mb-2">
                                            <img width="100%" src="../assets/image/logo/music.png">
                                            <div class="rc-header h1">Music</div>
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col-lg-6" v-for="music in musics" :key="music.id">
                                            <a href="#">
                                                <div style="padding: 4px 1.5px 2px 0">
                                                    <img class="rc-img" :src="music.image">
                                                    <div class="rc-coverImg"></div>
                                                    <div class="rc-name h5">{{music.name}}</div>
                                                    <label class="rc-ststusOnline" v-if="music.status != 1"></label>
                                                    <label class="rc-ststusOnline active" v-else></label>
                                                </div>
                                            </a>
                                        </div>
                                    </div>
                                </div>
                                <div style="padding:0 30px 0 10px">
                                    <div class="row" style="padding-left:7px">
                                        <div class="col-lg-12 mb-2">
                                            <img width="100%" src="../assets/image/logo/comedy.png">
                                            <div class="rc-header h1">Comedy</div>
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col-lg-6" v-for="comedy in comedys" :key="comedy.id">
                                            <a href="#">
                                                <div style="padding: 4px 1.5px 2px 0">
                                                    <img class="rc-img" :src="comedy.image">
                                                    <div class="rc-coverImg"></div>
                                                    <div class="rc-name h5">{{comedy.name}}</div>
                                                    <label class="rc-ststusOnline" v-if="comedy.status != 1"></label>
                                                    <label class="rc-ststusOnline active" v-else></label>
                                                </div>
                                            </a>
                                        </div>
                                    </div>
                                </div>

                                <div style="padding:0 30px 0 10px">
                                    <div class="row" style="padding-left:7px">
                                        <div class="col-lg-12 mb-2">
                                            <img width="100%" src="../assets/image/logo/food.png">
                                            <div class="rc-header h1">Food</div>
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col-lg-6" v-for="food in foods" :key="food.id">
                                            <a href="#">
                                                <div style="padding: 4px 1.5px 2px 0">
                                                    <img class="rc-img" :src="food.image">
                                                    <div class="rc-coverImg"></div>
                                                    <div class="rc-name h5">{{food.name}}</div>
                                                    <label class="rc-ststusOnline" v-if="food.status != 1"></label>
                                                    <label class="rc-ststusOnline active" v-else></label>
                                                </div>
                                            </a>
                                        </div>
                                    </div>
                                </div>
                                
                                <template slot="prev"><img class="prev" src="../assets/icon/arrowPrev.png"></template>
                                <template slot="next"><img class="next" src="../assets/icon/arrowNext.png"></template>
                            </carousel>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import carousel from 'vue-owl-carousel'
    export default {
        name: 'Recommend',
        components: { carousel },
        data(){
            return{
                games:[
                    {
                        id:1,
                        image:'https://cdn.pixabay.com/photo/2020/12/19/23/13/girls-5845644__340.jpg',
                        name:'BabyIceZaaaaaaaaaaaaaaaaaaa',
                        status: '1'
                    },
                    {
                        id:2,
                        image:'https://cdn.pixabay.com/photo/2020/12/29/22/22/doctor-5871743__340.jpg',
                        name:'BabyIceZa',
                        status: '1'
                    },
                    {
                        id:3,
                        image:'https://cdn.pixabay.com/photo/2020/05/25/15/17/hand-5219048__340.jpg',
                        name:'BabyIceZa',
                        status: '1'
                    },
                    {
                        id:4,
                        image:'https://cdn.pixabay.com/photo/2020/12/17/04/09/guanajuato-5838206__340.jpg',
                        name:'BabyIceZa',
                        status: '0'
                    }
                ],
                musics:[
                    {
                        id:1,
                        image:'https://cdn.pixabay.com/photo/2020/11/27/07/32/choir-5781096__340.jpg',
                        name:'TannTarnZa',
                        status: '0'
                    },
                    {
                        id:2,
                        image:'https://cdn.pixabay.com/photo/2017/06/21/22/40/guitar-2428921__340.jpg',
                        name:'TannTarnZa',
                        status: '0'
                    },
                    {
                        id:3,
                        image:'https://cdn.pixabay.com/photo/2020/06/20/16/32/dance-5321562__340.jpg',
                        name:'TannTarnZaaaaaaaaaaa',
                        status: '1'
                    },
                    {
                        id:4,
                        image:'https://cdn.pixabay.com/photo/2020/01/31/07/53/man-4807395__340.jpg',
                        name:'TannTarnZa',
                        status: '0'
                    }
                ],
                comedys:[
                    {
                        id:1,
                        image:'https://cdn.pixabay.com/photo/2020/05/17/20/21/cat-5183427__340.jpg',
                        name:'BabyIceZaaaaaaaaaaaaaaaaaaa',
                        status: '0'
                    },
                    {
                        id:2,
                        image:'https://cdn.pixabay.com/photo/2019/10/06/18/27/hemlock-4530921__340.jpg',
                        name:'BabyIceZa',
                        status: '0'
                    },
                    {
                        id:3,
                        image:'https://cdn.pixabay.com/photo/2020/11/28/19/18/girl-5785590__340.jpg',
                        name:'BabyIceZa',
                        status: '1'
                    },
                    {
                        id:4,
                        image:'https://cdn.pixabay.com/photo/2020/12/17/04/09/guanajuato-5838206__340.jpg',
                        name:'BabyIceZa',
                        status: '0'
                    }
                ],
                foods:[
                    {
                        id:1,
                        image:'https://cdn.pixabay.com/photo/2017/01/31/09/30/raspberry-2023404__340.jpg',
                        name:'TannTarnZa',
                        status: '1'
                    },
                    {
                        id:2,
                        image:'https://cdn.pixabay.com/photo/2017/10/09/19/29/eat-2834549__340.jpg',
                        name:'TannTarnZa',
                        status: '0'
                    },
                    {
                        id:3,
                        image:'https://cdn.pixabay.com/photo/2015/03/14/19/45/suit-673697__340.jpg',
                        name:'TannTarnZaaaaaaaaaaa',
                        status: '0'
                    },
                    {
                        id:4,
                        image:'https://cdn.pixabay.com/photo/2014/08/08/20/51/hunger-413685__340.jpg',
                        name:'TannTarnZa',
                        status: '0'
                    }
                ],
            }
        }
    }
</script>

<style lang="css" scoped>
@media screen and (min-width: 1200px){
    .h1{font-size: 23px;}
    .h2{font-size: 22px;}
    .h5{font-size: 13px;}

    .bg-rc{
        width: 100%;
        height: 416px;
        background-color: #24284b;
    }

    .rc-img{
        width: 100%;
        height: 89px;
        object-fit: cover;
        overflow: hidden;
        border-radius: 10px;
        padding:0 0 0 5px;
    }

    .rc-coverImg{
        position: absolute;
        top: 50px;
        left: 5px;
        right: 2px;
        bottom: 2px;
        z-index: 1;
        border-radius: 0 0 7px 7px;
        background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0),rgba(255, 255, 255, 0.2),rgba(255, 255, 255, 0.5),rgba(255, 255, 255, 0.8), #ffffff);
    }

    .rc-name{
        position: absolute;
        left: 13px;
        bottom: 0;
        z-index: 2;
        text-overflow: ellipsis;
        overflow: hidden; 
        width: 70%; 
        white-space: nowrap;
        color: #141621;
        font-family: 'kanitmedium';
    }

    .rc-ststusOnline{
        background-color: #d82a2a;
        opacity: 0;
        width: 8px;
        height: 8px;
        border-radius: 50%;
        position: absolute;
        right: 10px;
        bottom: 1px;
        z-index: 2;
    }

    .rc-ststusOnline.active{
        background-color: #0fc680;
        opacity: 1;
    }

    .rc-header{
        color: #fff;
        font-family: 'kanitmedium';
        position: absolute;
        top: 30px;
        left: 15px;
        z-index: 1;
    }
}
</style>