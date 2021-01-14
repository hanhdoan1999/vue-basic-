<template>
  <div >
    <h2>{{title}}</h2>    
    <el-container>
        <el-card class="mr-10 w-6/12" >
            <h2 class="mb-3">Component Parent 2</h2>
      <el-input type="text" v-model="ComponentParentValue"></el-input>
      <el-button class="mt-3" @click="ComponentChildValue=ComponentParentValue" type="success" >Click</el-button>
      </el-card>
    </el-container>
    <el-container>
    <!-- <ComponentChild2 :ComponentChildValue="ComponentChildValue" @input="ComponentParentValue=$event"/> -->
    <ComponentChild2 v-model="ComponentChildValue"/>
    </el-container>
  </div>
</template>

<script>
import ComponentChild2 from './ComponentChild2'
export default {
    props:["title"],
  data() {
    return {
      ComponentParentValue:"ComponentParentValue",
      ComponentChildValue:"",
    };
  },
  components: {
    ComponentChild2
  },
  watch:{
    ComponentChildValue(){
      this.ComponentParentValue=this.ComponentChildValue;
    }
  }
};
</script>

<style>
  .el-container {
    margin-bottom: 40px;
    margin-left:40px;
    margin-top: 40px;
  }
</style>
