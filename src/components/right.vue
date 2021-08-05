<template>
  <ul class="right">
    <item :aa=value v-for="(value,index) in contents" @cancel="cancel(index)" :key="index" ></item>
  </ul>
</template>
<script>
import item from './item'
export default {
  name: 'right',
  components: {item: item},
  props: {
    contents: {
      type: Array,
      required: true
    }
  },
  methods: {
    cancel (val) {
      this.$emit('cancel', val)
    }
  }
}
</script>
<style>
.right{width: 500px;height: 400px;border: gray solid 1px}
</style>
