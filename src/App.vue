<template>
  <div class="main">
    <HeaderSection :isActiveFormPurchase="isActiveFormPurchase" @updateIsActiveFormPurchase="updateIsActiveFormPurchase" :isActiveFormContact="isActiveFormContact" @updateIsActiveFormContact="updateIsActiveFormContact"/>
    <AboutSection/>
    <SliderSection/>
    <SellSection @updateIsActiveFormPurchase="updateIsActiveFormPurchase"/>
    <FooterSection @updateIsActiveFormPurchase="updateIsActiveFormPurchase" @updateIsActiveFormContact="updateIsActiveFormContact"/>
    <PurchaseForm :isActiveFormPurchase="isActiveFormPurchase" @updateIsActiveFormPurchase="updateIsActiveFormPurchase"/>
    <ContactForm  :isActiveFormContact="isActiveFormContact" @updateIsActiveFormContact="updateIsActiveFormContact"/>
    <BurgerMenu :isActiveBurgerMenu="isActiveBurgerMenu" @updateIsActiveBurgerMenu="updateIsActiveBurgerMenu" @updateIsActiveFormContact="updateIsActiveFormContact"/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import HomePage from './components/homePage/HomePage.vue'
import HeaderSection from './components/HeaderSection.vue';
import AboutSection from './components/AboutSection.vue';
import SliderSection from './components/SliderSection.vue';
import SellSection from './components/SellSection.vue';
import FooterSection from './components/FooterSection.vue';
import PurchaseForm from './components/PurchaseForm.vue';
import ContactForm from './components/ContactForm.vue';
import BurgerMenu from './components/BurgerMenu.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // HomePage
    HeaderSection,
    AboutSection,
    SliderSection,
    SellSection,
    FooterSection,
    PurchaseForm,
    ContactForm,
    BurgerMenu
  },
  data(){
    return{
      isActiveFormPurchase: false,
      isActiveFormContact: false,
      isActiveBurgerMenu: false
    }
  },
  methods:{
    updateIsActiveFormPurchase(newValue){
      this.isActiveFormPurchase = newValue;
    },
    updateIsActiveFormContact(newValue){
      this.isActiveFormContact = newValue;
    },
    updateIsActiveBurgerMenu(newValue){
      this.isActiveBurgerMenu = newValue;
    },
    closeModals(){
      this.isActiveFormPurchase = false;
    }
  }
}

</script>


<style>
*{
  margin:0;
  padding:0;
}
a{
  text-decoration: none;
}
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #fff;
}
html{
  scroll-behavior: smooth;
}
button{
  transition: scale 0.3s ease 0s;
}
button:hover{
  scale:1.05;
}
button:active{
  scale:0.95;
}
a{
  transition: scale 0.3s ease 0s;
}
a:hover{
  scale:1.1;
}
a:active{
  scale:0.9;
}
.main{
  overflow:hidden;
}
.wrapper{
  width: 80%;
  height: auto;
  margin: 0 auto;
  /* border: 2px solid pink; */
}
.row{
  display:flex;
}
.form{
  position: fixed;
  top:-100%;
  left:50%;
  opacity:0;
  transform: translate(-50%, -50%);

  display: flex;
  flex-direction: column;
  align-items: center;

  box-shadow: 0 0 15px 1px rgba(0,0,0,0.5);
  border-radius: 12px;
  z-index: 1000;
  background-color: #fff;
  padding: 30px 20px 0;
  transition: top 1s ease 0s, opacity 1s ease 0s;
}
.formActive{
  top:50%;
  left:50%;
  opacity:1;
}
.cross{
  position: absolute;
  top:5px;
  right:5px;
  width: 30px;
  height: 30px;
  cursor: pointer;
  transition: scale 0.3s ease 0s;
}
.cross:hover{
  scale:1.1;
}
.cross:active{
  scale:0.9;
}
.cross:before{
  content:'';
  position:absolute;
  top:50%;
  left:0;
  width: 20px;
  height: 2px;
  background-color:#000;
  transform: rotate(45deg);
  opacity: 0.2;
}
.cross:after{
  content:'';
  position: absolute;
  top:50%;
  left:0;
  width: 20px;
  height: 2px;
  background-color:#000;
  transform: rotate(-45deg);
  opacity: 0.2;
}
.form__title{
  align-items: center;
  justify-content: center;
  color:#37447E;
}
.form__title h2{
  margin: 0 10px;
  color:#37447E;
}
.form__logo{
  position: relative;
  width: 50px;
  height: 50px;
  overflow: hidden;
  opacity: 0.25;
}
.form__logo img{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: contain;
}
.form__item{
  width: 100%;
  margin: 10px 0;
}
.form__label{
  position: relative;
  display: block;
  width: 100%;
  text-align: start;
  text-transform:capitalize;
  margin: 0 0 10px;
}
.form__input{
  width: calc(100% - 24px);
  height: 40px;
  border: none;
  border-radius: 5px;
  box-shadow: 0 0 2px 1px rgb(105, 140, 147);
  padding: 0 10px;

  font-size:18px;
}
.form__input:focus{
  outline:none;
  box-shadow: 0 0 10px 1px #307ea9;
}
.form__submit{
  width: 120px;
  height: 50px;
  margin: 10px 0 0;
  background-color: #03a655;
  border: none;
  border-radius: 8px;
  color: #ebfdf4;
  text-transform: uppercase;
  font-weight: 700;
  box-shadow: 0 4px 0 0 #045f32;
  transition: all 0.4s ease 0s;
  cursor: pointer;
}
.form__submit:hover{
  scale:1;
  transform: translateY(2px);
  box-shadow: 0 2px 0 0 #045f32;
}
.form__submit:active{
  scale:1;
  transform: translateY(4px);
  box-shadow: 0 0px 0 0 #057e41;
}
.no-scroll {
  overflow: hidden;
}
@media(max-width:1280px){
  .about__bg{
    right:-10%;
  }
  .about__content p{
    width: 400px;
    font-size: 14px;
  }
  .slider__element-img{
      flex: 0 0 30%;
      height: 100%;
  }
  .slider__element-text{
      flex: 0 0 60%;
  }
}
@media(max-width:1024px){
  .header{
    height: 80vh;
  }
  .header__title h1{
    font-size:24px;
  }
  .header__body p{
    width: 400px;
    font-size: 14px;
    line-height:22px;
  }
  .about__bg{
    right:-30%;
  }
  .about__content{
    height: 70vh;
  }
  .about__title h2{
    font-size:24px;
  }
  .about__content p{
    border-radius: 10px;
    background-color: rgba(255,255,255,0.85);
  }
  .about__element-img{
    background-color: rgba(255,255,255,0.95);
  }
  .about__element-title{
    width: 105px;
    border-radius: 10px;
    background-color: rgba(255,255,255,0.95);
  }
  .about__element-text{
    width: 255px;
    border-radius: 10px;
    background-color: rgba(255,255,255,0.95);
  }
  .purchaseUIKitBtn{
    width: calc(150px + 4px);
    height: calc(36px + 4px);
  }
  .learnMoreBtn{
    width: 150px;
  }
  .slider__element-title{
    font-size: 24px;
  }
  .slider__element-body{
    font-size: 14px;
  }
}
@media(max-width:900px){
    .header__nav{
        display:none;
    }
    .header__body p{
      border-radius:10px;
      background-color:rgba(255,255,255,0.95);
      padding:10px;
    }
    .burger{
      display: block;
    }
    .slider__body{
      height: 400px;
    }
    .slider__content{
      width: 100%;
    }
    .slider__element{
      flex-direction: column;
      width:100%;
      height:400px;
      justify-content: center;
      /* height: 700px; */
    }
    .slider__element-img{
      width: 500px;
      flex: 0 0 200px;
    }
    .slider__element-text{
      flex: 0 0 auto;
    }
    .slider__element-title{
      width:100%;
      font-size: 20px;
      text-align: center;
      margin: 10px 0;
    }
    .slider__element-body{
      max-height:150px;
      overflow-y: scroll;
    }
    .sell__content{
      width: 80%;
      margin: 0 auto;
    }
    .sell__body{
      width:100%;
    }
}
@media(max-width:700px){
  .footer{
    height: 250px;
  }
  .footer__row{
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .footer__column{
    margin: 5px 0;
  }
  .footer__link{
    margin: 0 10px;
  }
  .contact__link{
    margin: 0 10px;
  }
}
@media(max-width:560px){
  .header__body{
    align-items: center;
  }
  .header__title{
    width:200px;
    line-height:24px;
  }
  .header__title h1{
    font-size: 18px;
    text-align: center;
  }
  .header__body p{
    max-width: 300px;
    width:100%;
  }
  .header__purchase{
    width: 100%;
    justify-content: center;
  }
  .purchaseUIKitBtn{
    font-size: 14px;
  }
  .about__content{
    align-items: center;
  }
  .about__content p{
    width: 100%;
    text-align:center;
    padding: 10px;
  }
  .about__elements{
    width:100%;
  }
  .about__element{
    flex: 0 0 50%;
    display:flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .about__element-title{
    width:100%;
    text-align:center;

  }
  .about__element-text{
    width: 100%;
    text-align:center;
  }
}
</style>
