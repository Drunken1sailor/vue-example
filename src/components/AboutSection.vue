<template>
    <div class="about wrapper" id="about">
        <div class="about__bg">
            <img :src="require('../assets/about/aboutImg.png')" alt="">
        </div>
        <div class="about__content row">
            <div class="about__title">
                <h2>Light, Fast & Powerful</h2>
            </div>
            <p class="about__p-1">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus </p>
            <p class="about__p-2">mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.</p>
            <div class="about__elements row">
                <div class="about__element">
                    <div class="about__element-img">
                        <img :src="require('../assets/about/Icon.png')" alt="icon">
                    </div>
                    <div class="about__element-title">Title Goes Here</div>
                    <div class="about__element-text">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. </div>
                </div>
                <div class="about__element">
                    <div class="about__element-img">
                        <img :src="require('../assets/about/Icon.png')" alt="icon">
                    </div>
                    <div class="about__element-title">Title Goes Here</div>
                    <div class="about__element-text">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{}
        }
    }
</script>
<style>
    .about{
        position: relative;
        /* overflow: hidden; */
    }
    .about__bg{
        position: absolute;
        z-index: 0;
        top:0;
        right:0;
        width: 540px;
        height: 100%;
    }
    .about__bg img{
        position: absolute;
        top:0;
        left:0;
        width: 100%;
        height: 100%;
        object-fit: contain;
    }
    .about__content{
        position: relative;
        z-index: 1;
        width: 100%;
        height: 100vh;
        flex-direction: column;
        justify-content: center;
        /* align-items:center; */
    }
    .about__title{
        margin: 50px 0 16px;
    }
    .about__title h2{
        font-size: 36px;
        color: #091133;
        text-align: start;
    }
    .about__content p{
        width: 540px;
        font-size: 16px;
        color:#6F7CB2;
        text-align: start;
        line-height: 26px;
    }
    .about__p-1{
        margin: 0 0 16px;
    }
    .about__p-2{
        margin: 0 0 40px;
    }
    .about__elements{
        display: block;
        justify-content: start;
        align-items: start;
    }
    .about__element{
        flex:0 0 255px;
    }
    .about__element-img{
        position: relative;
        width: 36px;
        height: 36px;
        margin:0 0 14px;
    }
    .about__element-img img{
        position: absolute;
        width: 100%;
        height: 100%;
        top:0;
        left:0;
        object-fit: cover;
    }
    .about__element-title{
        font-size: 15px;
        color: #091133;
        text-align: start;
        margin: 0 0 15px;
    }
    .about__element-text{
        width: 255px;
        font-size: 12px;
        color: #5D6970;
        text-align: start;
        margin:0;
    }
</style>