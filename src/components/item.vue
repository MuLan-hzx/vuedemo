<template>
  <div id="item" >
    <li>{{ aa.author }}--{{aa.content}}</li>
    <button @click="cancel">删除</button>
  </div>
</template>

<script>
export default {
  name: 'item',
  props: ['aa'],
  data () {
    return {

    }
  },
  methods: {
    cancel () {
      console.log(this.index)
      this.$emit('cancel', this.index)
    }
  }
}
</script>

<style scoped>
#item{width: 500px;height: 50px; line-height: 50px;font-size: 20px;border: coral solid 1px;display: flex;justify-content: space-between}
li{flex: 1}
button{width: 80px;height: 50px;line-height: 50px;font-size: 22px;color: red}
</style>
