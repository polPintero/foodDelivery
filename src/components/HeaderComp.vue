<template>
    <header class="header">
        <span class="header__title">FoodDeliver</span>
        <DeliveryChoice></DeliveryChoice>
        <NavComp></NavComp>
        <span class="header__phone">+380 67 451 99 57 | 24/7</span>
    </header>
</template>

<script>
import NavComp from './NavComp.vue';
import DeliveryChoice from './DeliveryChoice.vue';

export default {
    name: 'HeaderComp',
    components: { NavComp, DeliveryChoice }

}
</script>

<style lang="scss">
.header {
    position: fixed;
    left: 0;
    top: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 22px 30px;
    background: transparent;
    z-index: 1;

    &__title {
        font-family: 'TTTravels-Bold';
        margin-right: 28px;
    }

    &__phone {
        font-family: 'TTTravels-DemiBold';
        letter-spacing: 0.2px;
        font-size: 16px;
        line-height: 120%;
        margin-left: auto;

    }

    @media (max-width: 1060px) {
        justify-content: flex-start;

        &__phone {
            display: none;
        }
    }

    @media (max-width: 450px) {
        padding-top: 50px;

        &__title {
            position: absolute;
            left: 50%;
            top: 16px;
            transform: translateX(-50%);
        }
    }

}

.scrolling {
    .header {
        background: white;
        box-shadow: 0px 2px 14px rgba(0, 0, 0, 0.07);
    }
}
</style>