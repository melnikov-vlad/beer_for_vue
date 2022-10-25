<template>
  <div class="home">
    
    <vue_lesson02 label='JeckPot'/>
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import vue_lesson02 from '@/components/vue_lesson02.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld,
    vue_lesson02
    
  }
}
</script> 
