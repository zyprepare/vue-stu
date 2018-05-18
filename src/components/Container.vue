<script>
export default {
  props: [
    'content',
    'cdata'
  ],
  data() {
    return {
      coms: []
    }
  },
  render(h) {
    this.coms = [];
    for (var i = 0; i < this.content.length; i++) {
      this.coms.push(h(this.content[i], {
        props: { ...this.cdata[i], id: i}
      }));
    }

    return h('div', {}, this.coms);
  }
}
</script>
