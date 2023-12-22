<template>
    <form action="#" method="get" :class="['form','form-purchase',{'formActive':isActiveFormPurchase}]">
        <div class="cross" @click="closeFormPurchase"></div>
        <div class="form__title row">
            <div class="form__logo">
                <img :src="require('../assets/formPurchase/parallel-lines.png')" alt="logo">
            </div>
            <h2>Order Template</h2>
        </div>
        <div class="form__item row form__name">
            <label for="purchaseFormFirstName" class="form__label">Name</label>
            <input id="purchaseFormFirstName" name="first-name" type="text" class="form__input" placeholder="First">
            <input id="purchaseFormLastName" name="last-name" type="text" class="form__input" placeholder="Last">
        </div>
        <div class="form__item row form__gender">
            <input id="purchaseFormMale" type="radio" name="gender" value="male" class="form__gender-radio">
            <label for="purchaseFormMale" class="form__label form__gender-label">male</label>

            <input id="purchaseFormFemale" type="radio" name="gender" value="female" class="form__gender-radio">
            <label for="purchaseFormFemale" class="form__label form__gender-label">female</label>
        </div>
        <div class="form__item">
            <label for="purchaseFormPhone" class="form__label">phone</label>
            <input id="purchaseFormPhone" name="phone" type="tel" class="form__input" placeholder="Fill in number">
        </div>
        <div class="form__item">
            <label for="purchaseFormEmail" class="form__label">email address</label>
            <input id="purchaseFormEmail" type="text" class="form__input" placeholder="Fill in address">
        </div>
        <button type="submit" class="form__submit">continue to payment</button>
    </form>
</template>
<script>
    export default {
        props:{
            isActiveFormPurchase: Boolean
        },
        methods:{
            closeFormPurchase(){
                this.$emit('updateIsActiveFormPurchase', false);
            }
        }
    }
</script>
<style>
    .form-purchase{
        width: 350px;
        height: 450px;
    }
    .form__name{
        flex-wrap: wrap;
        justify-content: space-between;
    }
    .form__name .form__input{
        flex: 0 0 40%;
    }
    .form__gender{
        align-items: center;
    }
    .form__gender-radio{
        position: relative;
        opacity:0;
        margin: 0 5px 0 0;
    }
    .form__gender-label:before{
        content:'';
        position: absolute;
        top:50%;
        left:0;
        width: 15px;
        height: 15px;
        box-shadow: 0 0 2px 1px rgb(105, 140, 147);
        border-radius:50%;

        transform: translate(-125%, -50%);
    }
    .form__gender-label:after{
        content:'';
        position: absolute;
        top:4px;
        left: -16.8px;
        width: 11px;
        height: 11px;
        background-color: rgb(105, 140, 147);
        border-radius: 50%;
        scale:0;
        transition: scale 0.4s ease 0s;
    }
    .form__gender-radio:checked + .form__gender-label:after{
        scale:1;
    }
</style>