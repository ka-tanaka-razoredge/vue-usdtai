<template>
  <div ref="item" style="border: 1px solid red;">
    {{id}}
  </div>
</template>

<script>
  import {ref, defineComponent} from 'vue';

  export default defineComponent({
    name: "Item",
    props: {
      id: ""
    },
    methods: {
      getDiv: function() {
        return this.$refs.item.$el;
      }
    },
    mounted: (e) => {
      console.log(this.$refs.item);
    },
    getDiv: function() {
      console.log(this);
      console.log(this.$refs);
      return this.$refs;
    }
    
  });
</script>