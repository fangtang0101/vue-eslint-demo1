<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <template key="foo"> ... </template>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "home",
  components: {
    HelloWorld
  },
  computed:{
    foo(){
      return ''
    }
  },
  methods:{
    foo(){
      return 'abc'
    },
    getName(){
      console.log(1111)
    }
  },
}
</script>
