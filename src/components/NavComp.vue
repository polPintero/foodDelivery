<template>
    <nav class="nav">
        <ul>
            <li v-for="navItem in navList" :key="navItem.label"><a :href="navItem.url">{{ navItem.label }}</a></li>
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
    ul {
        display: flex;
        list-style: none;
        margin: 0;

        li {
            margin-right: 32px;

            &:last-child {
                margin-right: 0;
            }

            a {
                text-decoration: none;
                font-family: "TTTravels-Medium";
                font-size: 0.88rem;
                &:visited{
                    color: inherit;
                }
            }
        }
    }
}
</style>