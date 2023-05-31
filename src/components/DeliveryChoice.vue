<template>
    <form class="delivery-choice">
        <label class="delivery-choice__item"><input type="radio" name="delivery-choice"
                checked /><span>Доставка</span></label>
        <label class="delivery-choice__item"><input type="radio" name="delivery-choice" /><span>Самовивіз</span></label>
    </form>
</template>

<script>
export default {
    name: 'DeliveryChoice'
}
</script>

<style lang="scss">
.delivery-choice {
    display: flex;
    padding: 3px;
    min-width: fit-content;
    background: white;
    border-radius: 48px;
    border: 1px solid #e2e8f0;
    overflow: hidden;

    &__item {
        background-color: inherit;
        cursor: pointer;

        input {
            position: absolute;
            opacity: 0;

            &:checked+span {
                background: #5A30F0;
                color: white;
            }
        }

        span {
            font-family: 'TTTravels-DemiBold';
            font-size: 0.77rem;
            display: block;
            padding: 8px 12px;
            color: #636C81;
            border-radius: 34px;
        }


    }
}
</style>
