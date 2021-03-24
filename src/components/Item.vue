<template>
  <div ref="item" style="border: 1px solid red;">
    {{id}}
  </div>
</template>

<script>
  import {ref, onMounted, defineComponent} from 'vue';

  export default {
    name: "Item",
    props: {
      id: ""
    },
    setup(props) {
      const item = ref(null);

      console.log(props);
      const id = props.id;

      onMounted(() => {
        console.log("mounted");
//        console.log(item.value);
      });



      const getDiv = () => {
        console.log("------------");
        console.log(this);
        console.log(item);
        return item;
      };
      return {item, getDiv, id};
    },
  };
</script>