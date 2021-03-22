<template>
  <div id="app">
    <ListView ref="list_view" @arrive="doIt"></ListView>
  </div>
</template>

<script>
  import ListView from "./components/ListView.vue";

export default {
  name: "App",
  timer: {
  },
  tc: 0,
  props: {
  },
  methods: {
    doIt: function() {
      console.log('App.methods.doIt');
    }
  },
  components: {
    ListView
  },
  created: function() {
    const doRoutine = (function (e) {
      if (this.tc == 3) {
//        this.$emit('arrive');
//        console.log('here');
        this.$refs.list_view.dispatchEvent(new CustomEvent('arrive', null));
      }
      this.tc++;
    }).bind(this);
    this.tc = 0;
    this.timer = setInterval(doRoutine, 1000);
    console.log(this);
  }
};
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>