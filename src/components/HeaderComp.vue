<template>
    <header class="header">
        <span class="header__title">FoodDeliver</span>
        <NavComp></NavComp>
        <span class="header__phone">+380 67 451 99 57 | 24/7</span>
    </header>
</template>

<script>
import NavComp from './NavComp.vue';

export default {
    name: 'HeaderComp',
    components: { NavComp }

}
</script>

<style lang="scss">
.header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    padding: 22px 30px;
    background: transparent;
    display: flex;
    justify-content: space-between;

    &__title {
        font-family: 'TTTravels-Bold';
    }

    &__phone {
        font-family: 'TTTravels-DemiBold';
        letter-spacing: 0.2px;
        font-size: 16px;
        line-height: 120%;
        margin-left: auto;
    }

}

.scrolling {
    .header {
        background: white;
    }
}
</style>