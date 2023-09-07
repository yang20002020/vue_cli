<template>
  <div>
    <!-- {{message}} -->
    <!-- <element-view></element-view> -->
    <emp-view></emp-view>
  </div>
</template>

<script>
// import ElementView from "@/views/element/ElementView";
 import EmpView from "@/views/tlias/EmpView";
export default {
  // components: { ElementView },
  components: { EmpView },
  data() {
    return {
      message: "hello vue222",
    };
  },

  methods: {},
};
</script>

<style>
</style>
