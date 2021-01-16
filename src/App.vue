<template>
  <div id="app">
    <!-- <h1 class="text-center uppercase mt-10 font-semibold ">Ví dụ về giao tiếp giữa các component</h1>
    <ComponentA/>
    <hr>
    <h1 class="text-center uppercase mt-10 font-semibold ">Ví dụ về V-for + key</h1>
    <loop/>
    <hr>
    <h1 class="text-center uppercase mt-10 font-semibold ">Ví dụ về chuyển đổi dữ liệu giữa các component</h1>
    <ComponentParent1 :title="title"/>

    <ComponentParent2 :title="title2"/>

    <ComponentParent3 :title="title3"/> -->
    <TreeDemo/>

  </div>
</template>

<script>
// import ComponentA from './components/ComponentA.vue';
// import ComponentParent1 from './components/ComponentParent1'
// import ComponentParent2 from './components/ComponentParent2'
// import ComponentParent3 from './components/ComponentParent3'
// import Loop from './components/Loop.vue';
import TreeDemo from './components/TreeDemo'

export default {
  data() {
    return {
      title:"Chuyển đổi dữ liệu sử dụng v-bind và Event",
      title2:"Chuyển đổi dữ liệu sử dụng v-model",
      title3:"Chuyển đổi dữ liệu sử dụng .sync"
    };
  },
  name: "App",
  components: {
// ComponentParent1,
// ComponentParent2,
// ComponentParent3, 
//     ComponentA,
//     Loop,
    TreeDemo,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
  .el-container {
    margin-bottom: 40px;
    margin-left:40px;
  }
</style>
