<template>
    <main class="main-comp">
        <img class="main-comp__img" src="../assets/images/main.png" alt="main" />
        <div class="main-comp__descr">
            <div class="main-comp__descr--wrap">
                <h1>Доставка
                    готової їжі в Кієві</h1>
                <span>Ми пропонуємо доставку їжі прямо до ваших дверей. Насолоджуйтесь смачними стравами без необхідності
                    готувати
                    самостійно.</span>
            </div>
        </div>
    </main>
</template>

<script></script>

<style lang="scss">
.main-comp {
    display: flex;
    margin-block-end: 73px;

    &__img {
        display: block;
        max-width: 50vw;
    }

    &__descr {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        flex-grow: 2;

        &--wrap {
            width: 55%;

            h1 {
                margin: 0;
                margin-block-end: 30px;
                font-size: 4.22rem;
                font-weight: 400;
                line-height: 110%;

                @media (max-width: 1021px) {
                    font-size: 3.22rem;
                }

                @media (max-width: 921px) {
                    font-size: 2.2rem;
                }
            }
        }

    }

    @media (max-width: 721px) {
        flex-direction: column;

        &__img {
            max-width: 100vw;
            margin-bottom: 40px;
        }
    }
}
</style>
