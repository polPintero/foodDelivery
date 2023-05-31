<script setup>
import MainComp from "./components/MainComp.vue";
import CardsList from "./components/CardsList.vue";
import DeliveryBtn from "./components/DeliveryBtn.vue";
</script>

<script>
export default {
  name: 'App',
  data () {
    return {
      timeout: null,
      addingClass: 'scrolling'
    }
  },
  methods: {
    checkScrollPosition () {
      if (this.timeout) clearTimeout(this.timeout)
      setTimeout(() => {
        if (window.scrollY > 20) {
          document.body.classList.add(this.addingClass)
        } else if (window.scrollY <= 20) {
          document.body.classList.remove(this.addingClass)
        }
      }, 100)

    }
  },
  mounted () {
    window.addEventListener('scroll', this.checkScrollPosition)
  },
  beforeUnmount () {
    window.removeEventListener('scroll', this.checkScrollPosition)
  }
}
</script>

<template>
  <MainComp></MainComp>
  <CardsList></CardsList>
  <DeliveryBtn></DeliveryBtn>
</template>

<style ></style>
