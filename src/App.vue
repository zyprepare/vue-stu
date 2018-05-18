<template>
  <div id="app">
    <div :style="{marginBottom: '20px'}">
      <input value="Add Component" type="button" @click="addCom">
    </div>
    <my-container></my-container>
  </div>
</template>

<script>
import myContainer from "./components/MyContainer";
import Vue from "vue";
import vuex from "vuex";

Vue.use(vuex);

let styleObj = {
  width: "100px",
  height: "100px",
  backgroundColor: "#aaddee"
}

let store = new vuex.Store({
  state: {
    comList: [
      {
        styleObj: Object.assign({}, styleObj)
      }
    ]
  },
  mutations: {
    updateStyle(state, val) {
      state.comList = val;
    }
  }
});

export default {
  components: {
    myContainer
  },
  store,
  methods: {
    addCom: function() {
      this.$store.state.comList.push({styleObj: Object.assign({}, styleObj)});
    }
  }
};
</script>

