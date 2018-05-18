<template>
  <div>
    <div :style="styleObj">A Component</div>
  </div>
</template>

<script>
export default {
  props: [
    'idx'
  ],
  data() {
    return {
      styleObj: this.$store.state.comList[this.idx].styleObj
    }
  }
}
</script>
