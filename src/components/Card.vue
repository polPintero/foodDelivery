<template>
    <section class="card">
        <div v-if="card">
            <div>{{ card.title }}</div>
            <img :src="'src/assets/images/' + card.img" alt="">
        </div>
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
    border-radius: 8px;
}
</style>