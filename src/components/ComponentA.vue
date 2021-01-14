
<template>
<div>
    <h2 class="font-semibold">Giao tiếp cùng cấp</h2>
    <div>Component A</div>
  <p>Từ component A gọi ComponentB truyền vào thuộc tính name = "component-a" </p>
  <el-card>  <ComponentB :name="name" @selectedComponentB="handleEvent"></ComponentB></el-card>
  <p>Component B phát ra sự kiện 'selectedComponentB' qua $emit =>Component A xử lý :@selectedComponentB="handleEvent"</p>
</div>
</template>
<script>
import ComponentB from './ComponentB'
export default {
    components:{
      ComponentB
    },
  data() {
    return {
        name: 'component-a',
    }
  },
  methods: {
         handleEvent: function(data) {
          // in ra data từ component-b gửi lên
          alert(data)
          console.log(data);
      }
  }
}
</script>