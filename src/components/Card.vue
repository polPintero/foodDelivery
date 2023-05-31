<template>
    <section class="card">
        <div v-show="card" class="card__item">
            <div class="card__title">{{ card.title }}</div>
            <img :src="'/assets/images/' + card.img" alt="">
        </div>
        <div class="card__descr">{{ card.descr }}</div>
    </section>
</template>

<script>
export default {
    name: 'CardComp',
    props: {
        card: {
            type: Object,
            default: null
        }
    }
}
</script>

<style lang="scss">
.card {
    --transition-delay: 1s;
    --padding-card: 30px;
    position: relative;
    border-radius: 8px;
    background: #F3F6FB;
    height: 328px;
    width: max(20%, 300px);
    margin-left: auto;
    margin-right: auto;
    overflow: hidden;
    cursor: pointer;

    &__item {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: var(--padding-card) calc(var(--padding-card) + 25px);
        height: 100%;
        transition-duration: var(--transition-delay);
        transition-property: opacity;
    }

    &__title {
        text-align: center;
        font-size: 1.2rem;
        margin-bottom: 26px;
    }

    &__descr {
        display: block;
        position: absolute;
        background: #5A30F0;
        color: white;
        padding: var(--padding-card);
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        opacity: 0;
        transition-duration: var(--transition-delay);
        transition-property: opacity;
    }

    &:hover {
        .card__descr {
            opacity: 1;
        }
        .card__item {
            opacity: 0;
        }
    }
}
</style>