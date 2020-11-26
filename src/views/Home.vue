<template>
  <div class="home">
    <p>{{count}}</p>
    <button @click="add()">+++</button>
    <button @click="reduce()">---</button>
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
    // ...mapMutations(['add','reduce']), //辅助函数的使用方法
    add(){  //原生使用方法
      this.$store.commit('add')
    },
    reduce(){
      this.$store.commit('reduce')
    },
    
  },
  computed: {
    ...mapState(["count"]), //辅助函数的使用方法
    count () {  //原生使用方法
      return this.$store.state.count
    }
  }
}
</script>
