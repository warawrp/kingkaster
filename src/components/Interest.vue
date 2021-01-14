<template>
    <div id="interest">
        <div class="row" style="width:100%; padding-left:15px;">
            <div class="col-lg-12">
                <div class="row" style="padding-left:10px;">
                    <div class="col-lg-6">
                        <label class="rc-fontHeader h2 mr-3">หมวดหมู่ที่น่าสนใจ</label>
                        <a href="#">
                            <label class="it-fontMore h2 mr-2">More</label>
                            <div class="arrowMore"><img src="../assets/icon/arrowMore.png"></div>
                        </a>
                    </div>
                </div>
                <div style="padding: 0 50px 0 60px">
                    <carousel 
                        :autoplay="false" 
                        :loop="false" 
                        :nav="false" 
                        :items='6'
                        :responsive="{0:{items:1,nav:false},600:{items:4,nav:false},1200:{items:6,nav:false},1900:{items:8,nav:false}}" 
                        :dots="false" 
                        @changed="changed" @updated="updated">
                        <div style="padding:15px 30px 0 15px" v-for="cat in category" :key="cat.id">
                            <div class="row">
                                <div class="col-lg-12">
                                    <a href="#">
                                        <div style="padding: 4px 1.5px 2px 0">
                                            <div class="bg-it"></div>
                                            <img class="it-img" :src="cat.image">
                                            <div class="it-coverImg"></div>
                                            <div class="it-name h3">{{cat.name}}</div>
                                            <div class="it-caster">{{cat.video}}k Kasters</div>
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
</template>

<script>
    import carousel from 'vue-owl-carousel'
    export default {
        name:'Interest',
        components: { carousel },
        data(){
            return{
                category:[
                    {
                        id:'1',
                        name:'Film&Animation',
                        image:'https://cdn.pixabay.com/photo/2019/09/17/18/48/computer-4484282__340.jpg',
                        video:'123'
                    },
                    {
                        id:'2',
                        name:'Autos&Vehicles',
                        image:'https://cdn.pixabay.com/photo/2019/09/17/18/48/computer-4484282__340.jpg',
                        video:'234'
                    },
                    {
                        id:'3',
                        name:'Pet&Animals',
                        image:'https://cdn.pixabay.com/photo/2019/09/17/18/48/computer-4484282__340.jpg',
                        video:'345'
                    },
                    {
                        id:'4',
                        name:'Sports',
                        image:'https://cdn.pixabay.com/photo/2019/09/17/18/48/computer-4484282__340.jpg',
                        video:'456'
                    },
                    {
                        id:'5',
                        name:'Travel&Event',
                        image:'https://cdn.pixabay.com/photo/2019/09/17/18/48/computer-4484282__340.jpg',
                        video:'567'
                    },
                    {
                        id:'6',
                        name:'People&Blogs',
                        image:'https://cdn.pixabay.com/photo/2019/09/17/18/48/computer-4484282__340.jpg',
                        video:'789'
                    }
                ]
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

    .bg-it{
        width: 100%;
        height: 300px;
        background-color: #24284b;
        border-radius: 0 0 10px 10px;
        }

    .it-img{
        width: 100%;
        height: 241px;
        object-fit: cover;
        overflow: hidden;
        border-radius: 10px;
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;
        padding-right: 2px;
    }

    .it-coverImg{
        position: absolute;
        top: 15px;
        left: 0;
        right: 2px;
        bottom: 65px;
        z-index: 2;
        border-radius: 0 0 7px 7px;
        opacity: 0.57;
        background-image: linear-gradient(to bottom, 
        rgba(247, 32, 46, 0),
        rgba(247, 34, 48, 0.26),
        rgba(246, 49, 61, 0.62),
        rgba(245, 63, 74, 0.97), 
        #f55540);
    }
    
    .it-name{
        font-family: 'kanitregular';
        color: #fdce00;
        position: absolute;
        bottom: 25px;
        left: 10px;
        z-index: 1;
    }
    .it-caster{
        font-family: 'kanitregular';
        font-size: 14px;
        color: #fff;
        position: absolute;
        bottom: 15px;
        left: 10px;
        z-index: 1;
    }
    .arrowMore{
            position: absolute;
            top: 28px;
            left: 295px;
        }
}
</style>