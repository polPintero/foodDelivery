<template>
    <nav class="nav">
        <div class="nav__gamburger">
            <div class="nav__gamburger__line"></div>
            <div class="nav__gamburger__line"></div>
            <div class="nav__gamburger__line"></div>
        </div>
        <ul class="nav__content">
            <li class="nav__item" v-for="navItem in navList" :key="navItem.label"><a :href="navItem.url">{{ navItem.label
            }}</a></li>
        </ul>
    </nav>
</template>

<script>
export default {
    data () {
        return {
            navList: [
                { label: 'Заклади', url: '/' },
                { label: 'Доставка і оплата', url: '/' },
                { label: 'Акції', url: '/' },
                { label: 'Про нас', url: '/' },
            ]
        }
    }
}
</script>

<style lang="scss">
.nav {
    &__content {
        display: flex;
        list-style: none;
        margin: 0;
    }

    &__item {
        margin-right: 32px;

        &:last-child {
            margin-right: 0;
        }

        a {
            text-decoration: none;
            font-family: "TTTravels-Medium";
            font-size: 0.88rem;

            &:visited {
                color: inherit;
            }
        }
    }

    &__gamburger {
        display: none;
        flex-direction: column;
        justify-content: space-around;
        padding: 5px;
        width: 30px;
        aspect-ratio: 1;
        border-radius: 8px;
        border: 1px solid #404040;
        cursor: pointer;

        &__line{
            border: 1px solid #404040;
        }
    }

    @media (max-width: 1100px) {
        .nav {
            &__item {
                margin-right: 16px;
            }
        }
    }

    @media (max-width: 860px) {
        margin-left: auto;
            &__content {
                display: none;
            }

            &__gamburger {
                display: flex;
            }


    }



}</style>