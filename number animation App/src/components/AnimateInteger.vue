<template>
  <h1>{{ displayValue }}</h1>
</template>

<script>
import gsap from 'gsap'
export default {
  name: 'AnimageInteger',
  props: ['value'],
  data() {
    return {
      displayValue: this.value,
      tweenValue: this.value
    }
  },
  watch: {
    value() {
      //when value changes - do something
      gsap.to(this, {
        tweenValue: this.value,
        onUpdate: () => {
          this.displayValue = Math.ceil(this.tweenValue)
        }
      })
    }
  }
}
</script>

<style lang="scss" scoped></style>
