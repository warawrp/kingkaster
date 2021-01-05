<template>
    <div id="imageSlide">
        <div class="row">
            <div class="col-lg-12">
                <!-- <video playsinline autoplay muted loop>
                    <source src="../assets/video/Octagon.mp4" type="video/mp4">
                </video> -->
                <div>
                    <input type="radio" id="image1" name="image" checked>
                    <input type="radio" id="image2" name="image">
                    <input type="radio" id="image3" name="image">
                    <input type="radio" id="image4" name="image">
                    <input type="radio" id="image5" name="image">

                    <div class="container-fluid">
                        <div class="featured-wrapper">
                            <ul class="featured-list">
                                <li>
                                    <figure>
                                        <video playsinline autoplay muted loop>
                                            <source src="../assets/video/anime1.mp4" type="video/mp4">
                                        </video>
                                    </figure>
                                </li>
                                <li>
                                    <figure>
                                        <video playsinline autoplay muted loop>
                                            <source src="../assets/video/octagon.mp4" type="video/mp4">
                                        </video>
                                    </figure>
                                </li>
                                <li>
                                    <figure>
                                        <video playsinline autoplay muted loop>
                                            <source src="../assets/video/black.mp4" type="video/mp4">
                                        </video>
                                    </figure>
                                </li>
                                <li>
                                    <figure>
                                        <video playsinline autoplay muted loop>
                                            <source src="../assets/video/snowflakes.mp4" type="video/mp4">
                                        </video>
                                    </figure>
                                </li>
                                <li>
                                    <figure>
                                        <video playsinline autoplay muted loop>
                                            <source src="../assets/video/space.mp4" type="video/mp4">
                                        </video>
                                    </figure>
                                </li>
                            </ul>
                        </div>
                        <div class="titleImage"></div>
                        <ul class="thumb-list">
                            <li style="width:100px">
                                <label for="image1">
                                    <span class="outer">
                                        <span class="titleName">Title
                                            <span class="btnLiveNow">Live Now</span>
                                            <div class="titleDetail">Description</div>
                                        </span>
                                        <span class="inner"></span>
                                    </span>
                                </label>
                            </li>
                            <li style="width:100px">
                                <label for="image2">
                                    <span class="outer">
                                        <span class="titleName">Title
                                            <span class="btnLiveNow">Live Now</span>
                                            <div class="titleDetail">Description</div>
                                        </span>
                                        <span class="inner"></span>
                                    </span>
                                </label>
                            </li>
                            <li style="width:100px">
                                <label for="image3">
                                    <span class="outer">
                                        <span class="titleName">Title
                                            <span class="btnLiveNow">Live Now</span>
                                            <div class="titleDetail">Description</div>
                                        </span>
                                        <span class="inner"></span>
                                    </span>
                                </label>
                            </li>
                            <li style="width:100px">
                                <label for="image4">
                                    <span class="outer">
                                        <span class="titleName">Title
                                            <span class="btnLiveNow">Live Now</span>
                                            <div class="titleDetail">Description</div>
                                        </span>
                                        <span class="inner"></span>
                                    </span>
                                </label>
                            </li>
                            <li style="width:100px">
                                <label for="image5">
                                    <span class="outer">
                                        <span class="titleName">Title
                                            <span class="btnLiveNow">Live Now</span>
                                            <div class="titleDetail">Description</div>
                                        </span>
                                        <span class="inner"></span>
                                    </span>
                                </label>
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="cover-top"></div>
                <div class="cover-left"></div>
                <div class="cover-right"></div>
                <div class="cover-bottom"></div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ImageSlide",
    }
</script>

<style lang="css">
@media screen and (min-width: 1200px){
    .cover-top{
        height: 80px;
        width: 100%;
        z-index: 1;
        position: absolute;
        top: 0;
        left: 0;
        background-image: linear-gradient(to bottom, #141621,rgba(20, 22, 33, 1) 25%, rgba(20, 22, 33, 0.75) 50%, rgba(20, 22, 33, 0) 100%);
    }
    .cover-left{
        height: 623px;
        width: 100px;
        position: absolute;
        top: 0;
        left: 0;
        z-index: 0;
        background-image: linear-gradient(to right, #141621,rgba(20, 22, 33, 1) 25%, rgba(20, 22, 33, 0.75) 50%, rgba(20, 22, 33, 0) 100%);
    }

    .cover-right{
        height: 623px;
        width: 80px;
        position: absolute;
        top: 0;
        right: 0;
        z-index: 0;
        background-image: linear-gradient(to left, #141621,rgba(20, 22, 33, 1) 25%, rgba(20, 22, 33, 0.75) 50%, rgba(20, 22, 33, 0) 100%);
    }
    .cover-bottom{
        height: 80px;
        width: 100%;
        z-index: 0;
        position: absolute;
        top: 543px;
        left: 0;
        background-image: linear-gradient(to top, #141621,rgba(20, 22, 33, 1) 25%, rgba(20, 22, 33, 0.75) 50%, rgba(20, 22, 33, 0) 100%);
    }
    video {
    object-fit: cover;
    width: 100%;
    height: 623px;
    }

    .img1 {
        width: 100%;
        height: 623px;
        object-fit: cover;
    }


    /* RESET RULES
    –––––––––––––––––––––––––––––––––––––––––––––––––– */
    :root {
    --overlay: rgba(0, 0, 0, 0.75);
    }

    ul {
    list-style: none;
    padding: 0;
    }

    li{
        padding: 0;
        height: 97px;
    }

    .img1 {
    display: block;
    }

    label {
    display: block;
    cursor: pointer;
    }

    a {
    text-decoration: none;
    color: inherit;
    }

    input[type="radio"] {
    position: absolute;
    bottom: 0;
    left: -9999px;
    }

    .container-fluid {
    width: 100%;
    margin: 0;
    }

    /* SLIDESHOW
    –––––––––––––––––––––––––––––––––––––––––––––––––– */
    .featured-wrapper {
    position: relative;
    }

    .featured-wrapper .featured-list {
    display: grid;
    }

    .featured-wrapper .featured-list li {
    grid-column: 1;
    grid-row: 1;
    opacity: 0;
    transition: opacity 0.25s;
    }

    .thumb-list {
    position: absolute;
    z-index: 2;
    top: 90px;
    right: 325px;
    }

    .thumb-list label {
    display: grid;
    }

    .thumb-list .outer {
        grid-column: 1;
        grid-row: 1;
        width: 320px;
        height: 97px;
        color: #fff;
        
    }

    .thumb-list img {
    grid-column: 1;
    grid-row: 1;
    width: 100px;
    }

    .thumb-list .outer {
        display: grid;
        /* place-items: center; */
        transition: background 0.5s;
    }

    .thumb-list .inner {
        font-size: 18px;
        opacity: 0;
        transform: translateY(20px);
        transition: all 0.25s;
        font-family: 'kanitsemibold';
        color: #fff;
    }

    figure{
        width: 100%;
        height: 623px;
        margin: 0;
    }

    /* MIMIC CLICK EVENT
    –––––––––––––––––––––––––––––––––––––––––––––––––– */
    [id="image1"]:checked ~ .container-fluid .featured-list li:nth-child(1),
    [id="image2"]:checked ~ .container-fluid .featured-list li:nth-child(2),
    [id="image3"]:checked ~ .container-fluid .featured-list li:nth-child(3),
    [id="image4"]:checked ~ .container-fluid .featured-list li:nth-child(4),
    [id="image5"]:checked ~ .container-fluid .featured-list li:nth-child(5),
    [id^="image"]:checked ~ .container-fluid .arrows [for^="image"]:hover::before,
    [id^="image"]:checked ~ .container-fluid .arrows [for^="image"]:hover::after {
    opacity: 1;
    }

    [id="image1"]:checked ~ .container-fluid [for="image1"] .outer,
    [id="image2"]:checked ~ .container-fluid [for="image2"] .outer,
    [id="image3"]:checked ~ .container-fluid [for="image3"] .outer,
    [id="image4"]:checked ~ .container-fluid [for="image4"] .outer,
    [id="image5"]:checked ~ .container-fluid [for="image5"] .outer {
    background: var(--overlay);
    }

    [id="image1"]:checked ~ .container-fluid [for="image1"] .inner,
    [id="image2"]:checked ~ .container-fluid [for="image2"] .inner,
    [id="image3"]:checked ~ .container-fluid [for="image3"] .inner,
    [id="image4"]:checked ~ .container-fluid [for="image2"] .inner,
    [id="image5"]:checked ~ .container-fluid [for="image3"] .inner {
    opacity: 1;
    transform: none;
    }

    .titleImage {
        position: absolute;
        z-index: 1;
        top: 0;
        right: 0;
        width: 320px;
        height: 504px;
        margin: 69px 105px 50px 855px;
        padding: 44px 0;
        opacity: 0.92;
        border-radius: 10px;
        background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(20, 22, 33, 0.66) 19%, #141621 52%, rgba(0, 0, 0, 0.73) 87%, rgba(0, 0, 0, 0));
    }

    .titleName{
        margin: 18px 0 52px 31px;
        object-fit: contain;
        font-family: 'kanitsemibold';
        font-size: 18px;
    }

    .btnLiveNow{
        font-family: 'kanitlight';
        border-radius: 4px;
        background-color: #d50915;
        font-size: 13px;
        padding: 3px 5px;
        width: 72px;
        height: 27px;
    }


    .titleDetail{
        font-family: 'kanitlight';
        font-size: 18px;
    }
}
</style>