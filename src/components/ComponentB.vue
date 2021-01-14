<template lang="">
    <div>
       <div> {{name}}</div>
       <el-button type="success" @click="selectComponentB">selectComponentB</el-button>
    </div>
</template>
<script>
export default {
    props:["name"],
    methods: {
        selectComponentB: function() {
          // phát ra sự kiện 'selectedComponentB' với data là 'component-b đã được chọn'
          this.$emit('selectedComponentB', 'component-b đã được chọn');
      }
    },
}
</script>
<style lang="">
    
</style>