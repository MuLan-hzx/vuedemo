<template>
  <div id="app">
    <top/>
    <div id="container">
      <left @contentSubmit="insertContent"/>
      <right @cancel='cancel' v-bind:contents="contents"/>
    </div>
  </div>
</template>
<script>
import top from './components/top.vue'
import left from './components/left.vue'
import right from './components/right.vue'
export default {
  name: 'App',
  components: {
    top: top,
    left: left,
    right: right
  },
  data () {
    return {
      contents: [
        {
          author: 'Jack',
          content: 'I think VUE is awesome!'
        },
        {
          author: 'Mike',
          content: 'I think VUE is good!'
        },
        {
          author: 'James',
          content: 'I think VUE is garbage!'
        }
      ]
    }
  },
  methods: {
    insertContent: function (val) {
      console.log('APP:' + val)
      let array = val.split('-')
      this.contents.push(
        {author: array[0], content: array[1]}
      )
    },
    cancel (val) {
      this.contents.splice(val)
    }
  }
}
</script>
<style>
#app{height:1000px;display:flex;flex-direction:column;}
#container{height: 600px;display:flex;justify-content:space-around; align-items:center;background-color: antiquewhite;}
</style>
