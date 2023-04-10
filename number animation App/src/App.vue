<script>
import AnimateInteger from './components/AnimateInteger.vue'
import AnimateInteger2 from './components/AnimateInteger2.vue'
export default {
  name: 'App',
  components: {
    AnimateInteger,
    AnimateInteger2
  },
  data() {
    return {
      value: 10,
      formVal: -1,
      submitted: false
    }
  },
  methods: {
    formSubmition(values) {
      this.submitted = true
      this.formVal = values.year
      console.log(this.formVal)
    }
  }
}
</script>

<template>
  <div>
    <input type="number" name="number" v-model="value" />
    <AnimateInteger :value="value" />
    <form  @submit="formSubmition">
      <label for="test">Years </label>
      <input type="number" name="year" id="year" />
      <hr />
      <button type="submit">submit</button>
    </form>
    <AnimateInteger2 :value="formVal" :isSubmitted="submitted" />
  </div>
</template>

<style></style>
