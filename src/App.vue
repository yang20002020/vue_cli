<template>
  <div >
    {{message}}
   <element-view></element-view>
  </div>
</template>

<script>
import ElementView from "@/views/element/ElementView";
export default {
  components:{ElementView},
  data() {
    return {
      message:"hello vue222"
    }
  },

  methods: {
    
  }
 }
</script>

<style>

</style>
