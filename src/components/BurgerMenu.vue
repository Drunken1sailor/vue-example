<template>
    <div class="burger">
        <div class="burger__button" @click="showBurgerMenu">
            <div :class="['burger__button-straw', {'activeBurgerButton':isActiveBurgerMenu}]"></div>
        </div>
        <div :class="['burger__menu', {'activeBurgerMenu':isActiveBurgerMenu}]">
            <div class="nav__title main title burger__title">
                <h2>Landing</h2>
            </div>
            <a class="burger__link" href="#home" @click="closeBurgerMenu">Home</a>
            <a class="burger__link" href="#about" @click="closeBurgerMenu">About</a>
            <a class="burger__link" href="#" @click="openContactForm">Contact</a>
        </div>
    </div>
</template>
<script>
    export default {
        data(){
            return{

            }
        },
        props:{
            isActiveBurgerMenu:Boolean
        },
        methods:{
            openContactForm(){
                this.closeBurgerMenu();
                this.$emit('updateIsActiveFormContact',true);
            },
            showBurgerMenu(){
                console.log('showBurgerMenu');
                this.$emit('updateIsActiveBurgerMenu',!this.isActiveBurgerMenu);
            },
            closeBurgerMenu(){
                console.log('closeBurgerMenu');
                this.$emit('updateIsActiveBurgerMenu',false);
            }
        }
    }
</script>
<style>
    .burger{
        position: absolute;
        display: none;
    }
    .burger__button{
        position: fixed;
        z-index:200;
        top: 30px;
        right: 50px;
        width: 30px;
        height: 30px;
    }
    .burger__button-straw{
        position: absolute;
        top:10px;
        right:0;
        width: 100%;
        height: 3px;
        background-color: #111B47;
        border-radius: 10px;
        transition: background-color 0.1s ease 0s;
    }
    .burger__button-straw:before{
        content:'';
        position: absolute;
        top:-10px;
        right:0;
        width: 100%;
        height: 3px;
        background-color: #111B47;
        border-radius: 10px;
        transition: transform 0.5s ease 0s;
    }
    .burger__button-straw:after{
        content:'';
        position: absolute;
        top:10px;
        right:0;
        width: 100%;
        height: 3px;
        background-color: #111B47;
        border-radius: 10px;
        transition: transform 0.5s ease 0s;
    }
    .activeBurgerButton{
        background-color: transparent;
    }
    .activeBurgerButton.burger__button-straw:before{
        transform: translateY(10px) rotate(45deg);
    }
    .activeBurgerButton.burger__button-straw:after{
        transform: translateY(-10px) rotate(-45deg);
    }
    .burger__menu{
        position: fixed;
        top:-100%;
        left:0;
        width: 100%;
        height: 100vh;
        display:flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background-color: #e9f2f8;
        z-index: 100;
        transition: top 0.5s ease 0s;
    }
    .activeBurgerMenu{
        top:0;
    }
    .burger__title{
        top:50px;
    }
    .burger__link{
        width: 70%;
        height: 50px;
        background-color: #b1e1e9;
        border-radius: 20px;
        color: #505F98;
        margin: 0 0 30px;
        display:flex;
        justify-content: center;
        align-items:center;
    }
</style>