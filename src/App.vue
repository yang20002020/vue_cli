<template>
  <div>
    <!-- {{message}} -->
    <!-- <element-view></element-view> -->
<!--    员工管理-->
<!--    <emp-view></emp-view>-->
<!--   动态展示组件-->
    <router-view></router-view>
  </div>
</template>

<script>
// import ElementView from "@/views/element/ElementView";
//  import EmpView from "./views/tlias/EmpView.vue";
export default {
  // components: { ElementView },
  // components: { EmpView },
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
