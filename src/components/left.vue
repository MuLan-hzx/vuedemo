<template>
  <div class="left">
    <textarea cols="40" rows="20" v-model="content"/><br>
    <button @click="submit">Submit</button>
  </div>
</template>
<script>
export default {
  data () {
    return {
      content: ''
    }
  },
  methods: {
    submit () {
      console.log(this)
      this.$emit('contentSubmit', this.content)
    }
  }
}
</script>
<style>
.left{width: 500px;height: 400px;border: gray solid 1px;display: flex;flex-direction: column;align-items: flex-end}
textarea{width: 500px;height: 300px;resize: none; line-height: 40px; font-size: 25px}
button{width: 80px; height: 50px;line-height: 50px;font-size: 22px}
</style>
