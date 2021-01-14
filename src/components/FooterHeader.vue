<template>
    <div id="footerheader" >
        <div class="row" >
            <div class="col-lg-12 footerHeader">
                <div class="row pt-3" style="width:100%; padding-left:50px;">
                    <div class="col-lg-4">
                        <div>
                            <label class="titleEpisodes h4">Episodes</label>
                            <label><img src="../assets/icon/arrowHeader.png"></label>
                            <label class="fh-cat1 h4">Thai Main</label>
                            <label class="fh-cat2 h4">Thai Drama</label>
                        </div>
                        <div>
                            <label class="titleVariety h4">Variety show</label>
                            <label><img src="../assets/icon/arrowHeader.png"></label>
                            <label class="fh-cat1 h4">Hot Now</label>
                            <label class="fh-cat2 h4">Homemade</label>
                        </div>
                    </div>
                    <div class="col-lg-4 fh-line">
                        <div>
                            <label class="titleEpisodes h4">Episodes</label>
                            <label><img src="../assets/icon/arrowHeader.png"></label>
                            <label class="fh-cat1 h4">Thai Main</label>
                            <label class="fh-cat2 h4">Thai Drama</label>
                        </div>
                        <div>
                            <label class="titleVariety h4">Variety show</label>
                            <label><img src="../assets/icon/arrowHeader.png"></label>
                            <label class="fh-cat1 h4">Hot Now</label>
                            <label class="fh-cat2 h4">Homemade</label>
                        </div>
                    </div>
                    <div class="col-lg-4">
                        <div>
                            <label class="titleEpisodes h4">Episodes</label>
                            <label><img src="../assets/icon/arrowHeader.png"></label>
                            <label class="fh-cat1 h4">Thai Main</label>
                            <label class="fh-cat2 h4">Thai Drama</label>
                        </div>
                        <div>
                            <label class="titleVariety h4">Variety show</label>
                            <label><img src="../assets/icon/arrowHeader.png"></label>
                            <label class="fh-cat1 h4">Hot Now</label>
                            <label class="fh-cat2 h4">Homemade</label>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:"FooterHeader"
    }
</script>

<style lang="css" scoped>

@media screen and (min-width: 1200px){
    .h3, h3{font-size: 19px;}
    .h4, h4{font-size: 18px;}
    .h5, h5{font-size: 13px;}
    .h6, h6{
        font-size: 12px;
        margin: 0 !important;
    }
    .footerHeader {
        width: 100%;
        height: 141px;
        background-color: #202433;
        margin: 100vh 0 0 0;
    }

    .titleEpisodes {
        font-family: 'kanitsemibold';
        color: #ffffff;
        margin: 20px 10px 0  30px;
    }

    .titleVariety {
        font-family: 'kanitsemibold';
        color: #ffffff;
        margin: 20px 10px 0 30px;
    }

    .fh-cat1{
        font-family: 'kanitlight';
        color: #ffffff;
        margin: 0 20px 0 15px;
    }
    .fh-cat2{
        font-family: 'kanitlight';
        color: #ffffff;
    }

    .fh-line{
        /* position: absolute;
        top: 20px;
        right: 30px;
        width: 1px;
        height: 78px; */
        border-width: 1px;
        border-style: solid;
        border-image: 
            linear-gradient(
            to bottom, rgba(255, 255, 255, 0), #ffffff 53%, rgba(255, 255, 255, 0)) 1 100%;
    }
}
</style>