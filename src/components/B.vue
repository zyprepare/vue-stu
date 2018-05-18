<template>
  <div :style="{marginTop: '20px', marginBottom: '30px'}">
    style:
    <div>
      width : <input v-model="wid">
    </div>
    <div>
      height: <input v-model="hei">
    </div>
    <div>
      bgColor: <input v-model="bgColor">
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'idx'
  ],
  computed: {
    wid: {
      get() {
        return this.$store.state.comList[this.idx].styleObj.width
      },
      set(val) {
        this.$store.state.comList[this.idx].styleObj.width = val;
        this.$store.commit('updateStyle', this.$store.state.comList)
      }
    },
    hei: {
      get() {
        return this.$store.state.comList[this.idx].styleObj.height
      },
      set(val) {
        this.$store.state.comList[this.idx].styleObj.height = val;
        this.$store.commit('updateStyle', this.$store.state.comList)
      }
    },
    bgColor: {
      get() {
        return this.$store.state.comList[this.idx].styleObj.backgroundColor
      },
      set(val) {
        this.$store.state.comList[this.idx].styleObj.backgroundColor = val;
        this.$store.commit('updateStyle', this.$store.state.comList)
      }
    }
  }
}
</script>
