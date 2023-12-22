<template>
    <div class="sell">
        <div class="sell__content">
            <div class="sell__title">
                <h2>A Price To Suit Everyone</h2>
            </div>
            <div class="sell__body">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus </div>
            <div class="sell__price">$40</div>
            <p class="sell__price-p">UI Design Kit</p>
            <p class="sell__btn-p">See, One price. Simple.</p>
            <button class="purchaseBtn" @click="openPurchaseForm">Purchase Now</button>
        </div>
    </div>
</template>
<script>
    export default {
        methods:{
            openPurchaseForm(){
                this.$emit('updateIsActiveFormPurchase', true);
            }
        }
    }
</script>
<style>
    .sell{
        position: relative;
        width: 100%;
        height: 100vh;
        font-family: 'Roboto', sans-serif;
        background-color: #eff1fa;
    }
    .sell__content{
        position: relative;
        z-index: 1;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .sell__title{
        margin: 0 0 16px;
    }
    .sell__title h2{
        font-size: 36px;
        color:#091133;
    }
    .sell__body{
        width: 600px;
        height: 80px;
        font-size: 16px;
        color:#6F7CB2;
        margin: 0 0 35px;
    }
    .sell__price{
        font-size: 50px;
        color:#222F65;
    }
    .sell__price-p{
        font-size: 16px;
        color:#37447E;
        margin: 0 0 60px;
    }
    .sell__btn-p{
        font-size: 14px;
        color:#5D6970;
        margin:0 0 10px;
    }
</style>
