<template>
  <div ref="lv" style="border: 1px solid black;" @arrive="handle">
    ListView
  </div>
</template>

<script>
  export default {
  name: "ListView",
  props: {
    msg: String
  },
  methods: {
    dispatchEvent: function(e) {
      console.log(this);
      this.$refs.lv.dispatchEvent(new CustomEvent('arrive', null));
    },
    doIt: function(e) {
    },
    handle: function(e) {
      console.log('handle');
    }
  },
  mounted: function() {
  }
};
</script>