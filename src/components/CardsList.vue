<template>
    <div class="card-list" ref="cradList">
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
    },
    methods: {
        setObserver () {
            let options = {
                rootMargin: "0px",
                threshold: 0.1,
            };

            let observer = new IntersectionObserver((entries) => {
                entries.forEach(item => {
                    if (item.intersectionRatio < options.threshold) {
                        item.target.classList.remove('start')
                        return
                    }
                    item.target.classList.add('start')
                })
            }, options);
            observer.observe(this.$refs.cradList);
        }
    },
    mounted () {
        setTimeout(() => {
            this.setObserver()
        }, 100)
    }
}
</script>

<style lang="scss">
@mixin animation-func($size) {
    @for $i from 1 through 4 {
        .card:nth-child(#{$i}) {
            transform: translateY($i * $size);
            transition-duration: 0.5s;
        }
    }
}

.card-list {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: center;
    gap: 30px;
    margin: 0 60px 70px 60px;

    &.start {
        @include animation-func(0)
    }
}


@for $i from 1 through 4 {
    @include animation-func(80px)
}
</style>
