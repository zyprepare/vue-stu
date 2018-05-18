<template>
  <ul>
    <li v-for="(item, index) in $store.state.comList">
      <comp :idx="index"></comp>
      <styleCom :idx="index"></styleCom>
    </li>
  </ul>
</template>

<script>
import comp from './A.vue'
import styleCom from './B.vue'

export default {
  components: {
    comp,
    styleCom
  }
}
</script>
