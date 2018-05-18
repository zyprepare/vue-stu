<template>
  <div>
    <comp></comp>
    <styleCom></styleCom>
  </div>
</template>

<script>
import comp from './A.vue'
import styleCom from './B.vue'
import Vue from 'vue'
import vuex from 'vuex'

Vue.use(vuex)
let store = new vuex.Store({
  state: {
    styleObj: {
      width: '100px',
      height: '100px',
      backgroundColor: '#aaddee'
    }
  },
  mutations: {
    updateStyle (state, val) {
      state.styleObj = val
    }
  }
})

let store2 = new vuex.Store({
  state: {
    styleObj: {
      width: '100px',
      height: '100px',
      backgroundColor: '#aaddee'
    }
  },
  mutations: {
    updateStyle (state, val) {
      state.styleObj = val
    }
  }
})

let storeArr = [store, store2]
console.log()
export default {
  props: [
    'id'
  ],
  components: {
    comp,
    styleCom
  },
  store: storeArr[0]
}
</script>
