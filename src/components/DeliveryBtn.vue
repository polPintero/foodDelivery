<template>
    <button class="delivery-btn" ref="btn">
        Замовити доставку
    </button>
</template>

<script>
export default {
    name: 'DeliveryBtn',
    data () {
        return {
            timeout: null,
            btnStyles: null,
        }
    },
    methods: {
        behaviorBtnSet () {
            if (this.timeout) clearTimeout(this.timeout)
            setTimeout(() => {
                if (window.scrollY > 0) {
                    this.$refs.btn.style.setProperty('--btnTransform', 'translate(-50%, 25%)');
                    this.$refs.btn.style.setProperty('--widthBtn', '150px');
                } else if (window.scrollY <= 0) {
                    this.$refs.btn.style.setProperty('--btnTransform', 'translate(-50%, -25%)');
                    this.$refs.btn.style.setProperty('--widthBtn', '198px');

                }
            }, 200)

        }
    },
    mounted () {
        this.btnStyles = this.$refs.btn.computedStyleMap();
        window.addEventListener('scroll', this.behaviorBtnSet)
    },
    beforeUnmount () {
        window.removeEventListener('scroll', this.behaviorBtnSet)
    }
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
        transform: var(--btnTransform) rotate(calc(var(--degRotate) - calc(var(--degRotate) * 2)));
    }

    50% {
        transform: var(--btnTransform) rotate(var(--degRotate));
    }

    100% {
        transform: var(--btnTransform) rotate(calc(var(--degRotate) - calc(var(--degRotate) * 2)));
    }
}</style>