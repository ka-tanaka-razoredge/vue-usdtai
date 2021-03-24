<template>
  <div id="lv" ref="lv" style="border: 1px solid black;" @arrive="handle">
    ListView
  </div>
</template>

<script>
  import Vue, {createApp, defineComponent} from 'vue';
  import Item from './Item.vue';

  export default {
    name: "ListView",
    components: {
      Item
    },
    props: {
      msg: String
    },
    methods: {
      dispatchEvent: function(e) {
        console.log(this);
        this.$refs.lv.dispatchEvent(e);
      },
      doIt: function(e) {
      },
      handle: function(e) {
        let div = document.createElement('div');
        div.id = "item";
        div.innerHTML = 'innerHTML';
        this.$refs.lv.appendChild(div);

        createApp(Item, {id: 'ID'}).mount('#item');
      },
    },
    mounted: function() {
    }
};
</script>