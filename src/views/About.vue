<template>
  <div class="about">
    <p>{{count}}</p>
    <button @click="reduce()">--</button>
  </div>
</template>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import { mapMutations,mapState } from 'vuex'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  methods:{
    // ...mapMutations(['reduce']),
    reduce(){
      this.$store.commit('reduce')
    }
  },
  computed: {
    ...mapState(["count"]),
    // count () {
    //   return this.$store.state.count
    // }
  }
}
</script>