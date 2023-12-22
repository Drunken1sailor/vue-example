<template>
    <form action="#" :class="['form', 'form__contact', {'formActive':isActiveFormContact}]">
        <div class="cross" @click="closeFormContact"></div>
        <div class="form__title row">
            <div class="form__logo">
                <img :src="require('../assets/formPurchase/parallel-lines.png')" alt="logo">
            </div>
            <h2>Contact Us</h2>
        </div>
        <div class="form__item">
            <label for="contactFormFullname" class="form__label">full name</label>
            <input id="contactFormFullname" name="fullName" type="text" class="form__input">
        </div>
        <div class="form__item">
            <label for="contactFormPhone" class="form__label">phone</label>
            <input id="contactFormPhone" name="phone" type="phone" class="form__input">
        </div>
        <div class="form__item">
            <label for="contactFormEmail" class="form__label">email</label>
            <input id="contactFormEmail" name="email" type="text" class="form__input">
        </div>
        <div class="form__item">
            <label for="contactFormTextarea" class="form__label">message</label>
            <textarea name="message" id="contactFormTextarea" rows="6" class="form__textarea"></textarea>
        </div>
        <button type="submit" class="form__submit">submit</button>
    </form>
</template>
<script>
    export default {
        data(){
            return{}
        },
        methods:{
            closeFormContact(){
                this.$emit('updateIsActiveFormContact',false);
            }
        },
        props:{
            isActiveFormContact:Boolean
        }
    }
</script>
<style>
    .form__contact{
        width: 450px;
        height: 580px;
    }
    .form__textarea{
        width: calc(100% - 24px);
        border: none;
        border-radius: 5px;
        box-shadow: 0 0 2px 1px rgb(105, 140, 147);
        padding: 10px;
        font-size:14px;
    }
    .form__textarea:focus{
        outline:none;
        box-shadow: 0 0 10px 1px #307ea9;
    }
</style>