<template>
    <button class="delivery-btn" ref="btn">
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
    --btnTransform: translate(-50%, -25%);
    --degRotate: 45deg;
    --widthBtn: 198px;

    position: fixed;
    bottom: 0;
    left: 50%;
    transform: var(--btnTransform);
    aspect-ratio: 1;
    width: var(--widthBtn);
    font-family: 'TTTravels-DemiBold';
    line-height: 130%;
    letter-spacing: 0.03rem;
    background: var(--bg-main);
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
    transition-duration: 0.8s;
    cursor: pointer;
}

.scrolling {
    .delivery-btn {
        bottom: -100px;
        --widthBtn: 158px;

        &:hover {
            --btnTransform: translate(-50%, -65%);
        }
    }
}

@keyframes rotateBtn {
    0% {
        transform: var(--btnTransform) rotate(calc(var(--degRotate) - calc(var(--degRotate) * 2)));
    }

    50% {
        transform: var(--btnTransform) rotate(var(--degRotate));
    }

    100% {
        transform: var(--btnTransform) rotate(calc(var(--degRotate) - calc(var(--degRotate) * 2)));
    }
}
</style>