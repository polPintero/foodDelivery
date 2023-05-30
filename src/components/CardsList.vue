<template>
    <div class="card-list">
        <Card v-for="card in cardList" :key="card.title" :card="card"></Card>
    </div>
</template>

<script>
import Card from './Card.vue'

export default {
    name: 'CardList',
    components: { Card },
    data () {
        return {
            cardList: [
                {
                    title: 'Висока якість продукції',
                    img: 'check.svg',
                    descr:
                        'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.'
                },
                {
                    title: 'Різноманітність страв',
                    img: 'bowl.svg',
                    descr:
                        'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.'
                },
                {
                    title: 'Швидка доставка',
                    img: 'rocket.svg',
                    descr:
                        'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.'
                },
                {
                    title: 'Працюємо цілодобово',
                    img: 'clock.svg',
                    descr:
                        'Наша доставка гарантує вам високу якість продуктів.  Кожна страва, яку ми готуємо, пройшла строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.'
                }
            ]
        }
    }
}
</script>

<style lang="scss">
.card-list {
    margin: 0 60px 70px 60px;
    display: grid;
    grid-template-columns:repeat(auto-fill, minmax(300px, 1fr));
    gap: 40px;
}
</style>
