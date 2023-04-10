<template>
    
    <h2 v-if="formSubmitted">{{ displayValue }}</h2>
    <h2 v-else>--</h2>
  </template>
  
  <script>
  import gsap from 'gsap'
  export default {
    name: 'AnimageInteger2',
    props: ['value', 'isSubmitted'],
    data() {
      return {
        displayValue: this.value,
        tweenValue: this.value,
        formSubmitted: this.isSubmitted
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
  