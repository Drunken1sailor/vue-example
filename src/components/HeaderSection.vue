<template>
    <div class="header" id="home">
        <div class="header__bg">
            <img :src="require('../assets/header/headerBG.png')" alt="background image">
        </div>
        <div class="header__nav nav row">
            <div class="nav__links row">
                <a class="nav__link" href="#home">Home</a>
                <a class="nav__link" href="#about">About</a>
                <a class="nav__link" href="#" @click="openContactForm">Contact</a>
            </div>
            <div class="nav__title main title">
                <h2>Landing</h2>
            </div>
            <div class="nav__btn btn">
                <button class="purchaseBtn" @click="openPurchaseForm">Buy Now</button>
            </div>
        </div>
        <div class="wrapper header__content">
            <div class="header__body">
                <div class="header__title"><h1>Introduce Your Product Quickly & Effectively</h1></div>
                <p class="header__p-1">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus </p>
                <p class="header__p-2">mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.</p>
                <div class="header__purchase row">
                    <button class="purchaseUIKitBtn" @click="openPurchaseForm">Purchase UI Kit</button>
                    <a class="learnMoreBtn" href="#about">Learn More</a> 
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                isActiveBurgerMenu: false 
            }
        },
        methods:{
            openPurchaseForm(){
                this.$emit('updateIsActiveFormPurchase', true)
            },
            openContactForm(event){
                event.preventDefault();
                this.$emit('updateIsActiveFormContact', true)
            }
        },
        props:{
            isActiveFormPurchase:Boolean,
            isActiveFormContact:Boolean
        }
    }
</script>
<style>
    .header{
        position: relative;
        width: 100%;
        height: 150vh;
        overflow: hidden;
    }
    .header__bg{
        width: 100%;
        height: 100%;
        position: absolute;
        top:0;
        left:0;
        z-index: 0;
    }
    .header__bg img{
        position: absolute;
        top:0;
        right:0;
        width: auto;
        height: 100%;
        object-fit: cover;
        margin: 0;
        transform: translate(25%, -5%);
    }
    .header__content{
        position: relative;
        width: 100%;
        min-height: 100%;
        z-index: 1;
        display: flex;
        flex-direction: column;
    }
    .header__nav{
        position:fixed;
        top:0;
        left:50%;
        transform: translateX(-50%);
        z-index: 100;
        width: 80%;
        height: 55px;
        align-items: center;
        justify-content: space-between;
    }
    .nav__link{
        color: #505F98;
        margin: 0 50px 0 0;
        transition: all 0.3s ease 0s;
    }
    .nav__link:hover{
        /* box-shadow: 0 0 25px 10px #70ddfe;
        background-color: #70ddfe; */
        scale:1.1;
        color: #01bdfb;
    }
    .nav__title{
        position: absolute;
        left:50%; top:10px;
        height:35px;
        transform: translateX(-50%);
        font-size: 18px;
        color: #37447E;
    }
    .purchaseBtn{
        width: 160px;
        height: 26px;
        background-color: #111B47;
        color:#fff;
        border:none;
        border-radius:2px;
        cursor:pointer;
    }
    .header__body{
        position: relative;
        width: 100%;
        flex: 1 1 100%;
        display:flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        text-align: start;
    }
    .header__title{
        width: 540px;
        margin: 0 0 20px;
        line-height: 50px;
    }
    .header__body p{
        width: 540px;
        font-size: 18px;
        color:#505F98;
        line-height: 32px;
    }
    .header__p-1{
        margin: 0 0 20px;
    }
    .header__p-2{
        margin: 0 0 70px;
    }
    .purchaseUIKitBtn{
        width: 190px;
        height: 36px;
        border:none;
        border-radius:2px;
        background-color: #111B47;
        color:#fff;
        font-size: 16px;
        margin: 0 30px 0 0;
        cursor: pointer;
    }
    .learnMoreBtn{
        width: 190px;
        height: 36px;
        border-radius:2px;
        border: 2px solid #111B47;
        background-color: #fff;
        font-size: 16px;
        color:#000;
        display: flex;
        justify-content: center;
        align-items:center;
    }
</style>