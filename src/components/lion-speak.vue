<template lang="">
    <div>
    <el-card>
     <h2 class="">Lion say</h2>
     <div>
         <el-input type="textarea" :value="lionText" @input="(event)=>$emit('update:lionText',event.target.value)"></el-input>      
     </div>
     </el-card>
    </div>
</template>
<script>
export default {
  props: ["lionText"],
  // model:{
  //     prop:"lionText",
  //     value:"input"
  // }
};
</script>
<style lang="">
</style>