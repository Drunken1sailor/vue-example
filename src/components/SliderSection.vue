<template>
    <div class="slider">
        <div class="slider__content wrapper">
            <div class="slider__goPrevBtn slider__arrow">
                <button class="slider__button" @click="goPrev">
                    <img :src="require('../assets/slider/left-arrow.png')" alt="<">
                </button>
            </div>
            <div ref="sliderBody" class="slider__body row" @wheel="handleMouseWheel" @touchStart="handleTouchStart">
                <div 
                ref="sliderElements" 
                :class="['slider__element', 'row', {'active' : (element.id == currentIndex), 'goLeft':(element.id < currentIndex), 'goRight':(element.id > currentIndex)}]" 
                v-for="element in sliderElements" 
                :key="element.id"
                >
                    <div class="slider__element-img column">
                        <img :src="element.img" alt="image">
                    </div>
                    <div class="slider__element-text column">
                        <div class="slider__element-title">{{ element.title }}</div>
                        <div class="slider__element-body">{{ element.body }}</div>
                    </div>
                </div>
            </div>
            <div class="slider__goNextBtn slider__arrow">
                <button class="slider__button" @click="goNext">
                    <img :src="require('../assets/slider/right-arrow.png')" alt=">">
                </button>
            </div>
        </div>
        <div class="slider__bar">
            <div 
            :class="['slider__straw', {'active' : (element.id == currentIndex)}]"
            v-for="element in sliderElements"
            :key="element.id"
            @click="goTo(element.id)">
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                sliderElements:[
                    {id:0, img:require('@/assets/slider/sliderImg1.png'), title:'Light, Fast & Powerful', body:'Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.'},
                    {id:1, img:require('@/assets/slider/sliderImg2.png'), title:'Light, Fast & Powerful', body:'Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.'},
                    {id:2, img:require('@/assets/slider/sliderImg3.png'), title:'Light, Fast & Powerful', body:'Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.'},
                ],
                currentIndex: 1,
                touchStart: 0,
                touchEnd: 0
            }
        },
        methods:{
            goPrev(){
                if(this.currentIndex > 0){
                    this.currentIndex--;
                } else {
                    this.currentIndex = this.sliderElements.length - 1;
                }
            },
            goNext(){
                if(this.currentIndex < this.sliderElements.length - 1){
                    this.currentIndex++;
                } else {
                    this.currentIndex = 0;
                }
            },
            goTo(elementId){
                this.currentIndex = elementId;
            },
            handleMouseWheel(event){
                event.preventDefault();
                if(event.deltaY > 3 && event.deltaY < 6 && event.deltaX == 0){
                    this.currentIndex < this.sliderElements.length - 1 ? this.currentIndex++ : this.currentIndex = 0;
                    console.log(' + ',event);
                } else if (event.deltaY < -3 && event.deltaY > -6 && event.deltaX == 0){
                    this.currentIndex > 0 ? this.currentIndex-- : this.currentIndex = this.sliderElements.length - 1;
                    console.log(' - ',event);
                }
            }
            ,handleTouchStart(event){
                console.log(event)
            }
        }
    }
</script>
<style>
    .slider{
        width: 100%;
        /* height: 500vh; */
        /* background-color: blanchedalmond; */
        overflow: hidden;
        padding: 150px 0;
    }
    .slider__content{
        display: flex;
        align-items: center;
    }
    .slider__body{
        position: relative;
        height: 315px;
        width:100%;
        /* border:2px solid red; */
        /* overflow-x: scroll; */
        overflow: hidden;
        /* border: 2px solid black; */
    }
    .slider__arrow{
        width: 40px;
        height: 40px;
        position: relative;
        margin: 0 25px;
        opacity: 0.1;
        transition: all 0.3s ease 0s;
    }
    .slider__arrow:hover{
        scale:1.1;
        opacity: 0.2;
    }
    .slider__arrow:active{
        scale:0.9;
        opacity: 0.3;
    }
    .slider__button{
        width: 100%;
        height: 100%;
        position: relative;
        border: none;
        background-color: transparent;
        cursor: pointer;
    }
    .slider__button img{
        width: 100%;
        height: 100%;
        position: absolute;
        top:0;
        left:0;
        object-fit:contain;
    }
    .slider__bar{
        width: auto;
        height: 2px;
        display: flex;
        justify-content:center;
        margin: 30px 0 0;
    }
    .slider__straw{
        width: 60px;
        height: 3px;
        background-color: #000;
        border-radius: 20px; 
        margin: 0 10px;
        cursor: pointer;
        transition: all 0.5s ease 0s;
        opacity:0.1
    }
    .slider__straw:hover{
        opacity:0.5;
        scale:1.1;
    }
    .slider__straw:active{
        scale:0.9;
        opacity: 0.3;
    }
    .slider__straw.active{
        opacity:0.3;
    }
    .slider__element{
        position:absolute;
        height: 315px;
        top:0;
        left:0;
        min-width: 100%;
        justify-content: space-around;
        align-items: center;
        transition: transform 0.9s ease 0s;
    }
    .slider__body .active{
        transform: translateX(0);
    }
    .slider__body .goLeft{
        transform: translateX(-100vw);
    }
    .slider__body .goRight{
        transform: translateX(100vw);
    }
    .slider__element .column{
        text-align: left;
    }
    .slider__element-img{
        position:relative;
        height: 100%;
        flex: 0 0 480px;
    }
    .slider__element-img img{
        position: absolute;
        width: 100%;
        height: 100%;
        left: 0;
        right:0;
        object-fit: contain;
    }
    .slider__element-text{
        flex:0 0 450px;
    }
    .slider__element-title{
        font-size: 36px;
        color:#091133;
        margin: 0 0 16px;
    }
    .slider__element-body{
        width: 100%;
        font-size: 16px;
        color:#6F7CB2;
        line-height: 26px;
        text-align:justify;
    }
</style>
