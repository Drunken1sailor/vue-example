<template>
    <footer class="footer">
        <div class="wrapper">
            <div class="footer__row row">
                <div class="brand footer__column">©2023 Yourcompany</div>
                <div class="title footer__column"><h2>Landing</h2></div>
                <button class="purchaseBtn footer__column" @click="openPurchaseForm">Purchase Now</button>
            </div>
            <div class="straw"></div>
            <div class="footer__row row">
                <div class="nav__links footer__links footer__column">
                    <a href="#home" class="nav__link footer__link">Home</a>
                    <a href="#about" class="nav__link footer__link">About</a>
                    <a href="#" class="nav__link footer__link" @click="openContactForm">Contact</a>
                </div>
                <div class="contacts footer__column row">
                    <a class="contact__link" href="#">
                        <img :src="require('../assets/footer/facebook.png')" alt="facebook">
                    </a>
                    <a class="contact__link" href="#">
                        <img :src="require('../assets/footer/linkedin.png')" alt="facebook">
                    </a>
                    <a class="contact__link" href="#">
                        <img :src="require('../assets/footer/twitter.png')" alt="facebook">
                    </a>
                    <a class="contact__link" href="#">
                        <img :src="require('../assets/footer/youtube.png')" alt="facebook">
                    </a>
                    <a class="contact__link" href="#">
                        <img :src="require('../assets/footer/instagram.png')" alt="facebook">
                    </a>
                </div>
            </div>
        </div>
    </footer>
</template>
<script>
    export default {
        methods:{
            openPurchaseForm(){
                this.$emit('updateIsActiveFormPurchase', true)
            },
            openContactForm(event){
                event.preventDefault();
                this.$emit('updateIsActiveFormContact', true)
            }
        }
    }
</script>
<style>
    .footer{
        position: relative;
        z-index:1;
        width: 100%;
        height: 160px;
        background-color: #E7ECFF;
        padding: 60px 0 0;
        overflow: hidden;
    }
    .footer__row{
        justify-content: space-between;
    }
    .straw{
        width: 100%;
        height: 1px;
        background-color: #CDD1D4;
        margin: 40px 0 20px;
    }
    .footer__link{
        color:#929ECC;
    }
    .contact__link{
        display: block;
        position: relative;
        top:0;
        left:0;
        width: 15px;
        height: 15px;
        margin: 0 0 0 30px;
    }
    .contact__link img{
        position:absolute;
        top:0;
        left:0;
        width: 100%;
        height: 100%;
        object-fit: contain;
    }
    .contact__link:hover{
        scale:1.3;
    }
</style>