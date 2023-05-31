<template>
    <button class="delivery-btn">
        Замовити доставку
    </button>
</template>

<script>
export default {
    name: 'DeliveryBtn',
}
</script>

<style lang="scss">
.delivery-btn {
    position: fixed;
    bottom: 0;
    left: 50%;
    aspect-ratio: 1;
    width: 195px;
    font-family: 'TTTravels-DemiBold';
    line-height: 130%;
    letter-spacing: 0.03rem;
    background: #5A30F0;
    color: white;
    text-transform: uppercase;
    padding: 50px 25px;
    border-radius: 50%;
    border: none;
    outline: none;
    animation-name: rotateBtn;
    animation-duration: 10s;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
    cursor: pointer;
}
@keyframes rotateBtn {
    0% {
        transform: translate(-50%, -50%) rotate(-45deg);
    }
    50% {
        transform: translate(-50%, -50%) rotate(45deg);
    }
    100% {
        transform: translate(-50%, -50%) rotate(-45deg);
    }
}
</style>