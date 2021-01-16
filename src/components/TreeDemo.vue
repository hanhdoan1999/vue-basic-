<template>

<div class="custom-tree-container">
  <div class="">
    <p>Using scoped slot</p>
<el-card class="w-1/5">
        <el-tree
      :data="data"
      node-key="id"
      default-expand-all
      :expand-on-click-node="false">
      <span class="custom-tree-node" slot-scope="{ node, data }">
        <span> <i
        class="el-icon-document el-input__icon"
        slot="suffix">
       </i> {{ node.label}}</span>
        
         <el-tooltip  placement="bottom-end" effect="dark" v-if="isShow">
       <div class=" flex flex-col" slot="content" > 
           <el-button class="buttonCus"  @click="() => append(data)" icon="el-icon-plus">Thêm tài liệu</el-button> 
           <el-button class="buttonCus" @click="() => remove(node, data)" icon="el-icon-delete">Xóa tài liệu</el-button>       
            <!-- <el-button
            type="text"
            size="mini"
            @click="() => append(data)">
            Append
          </el-button> -->
          <!-- <el-button
            type="text"
            size="mini"
            @click="() => remove(node, data)">
            Delete
          </el-button> -->
          </div>
         
      </el-tooltip>
      <span @click="!isShow"><i class="el-icon-more-outline transform rotate-90" slot="append" ></i></span> 
      </span>
    </el-tree>
</el-card>
  </div>
</div>
    
</template>
<script>
  let id = 1000;

  export default {
    data() {
      const data = [{
        id: 1,
        label: 'Tài liệu mới 1',
        children: [{
          id: 4,
          label: 'Tài liệu mới 1-1',
          children: [{
            id: 9,
            label: 'Tài liệu mới 1-1-1'
          }, {
            id: 10,
            label: 'Tài liệu mới 1-1-2'
          }]
        }]
      }, {
        id: 2,
        label: 'Tài liệu mới 2',
        children: [{
          id: 5,
          label: 'Tài liệu mới 2-1'
        }, {
          id: 6,
          label: 'Tài liệu mới 2-2'
        }]
      }, {
        id: 3,
        label: 'Tài liệu mới 3',
        children: [{
          id: 7,
          label: 'Tài liệu mới 3-1'
        }, {
          id: 8,
          label: 'Tài liệu mới 3-2'
        }]
      }];
      return {
          isShow:false,
        data: JSON.parse(JSON.stringify(data))
    
      }
    },

    methods: {
      
      append(data) {
        const newChild = { id: id++, label: 'Tài liệu mới', children: [] };
        if (!data.children) {
          this.$set(data, 'children', []);
        }
        data.children.push(newChild);
      },

      remove(node, data) {
        const parent = node.parent;
        const children = parent.data.children || parent.data;
        const index = children.findIndex(d => d.id === data.id);
        children.splice(index, 1);
      },

    //   renderContent(h, { node, data, store }) {
    //     return (
    //       <span class="custom-tree-node">
    //         <span>{node.label}</span>
    //         <span>
    //           <el-button size="mini" type="text" on-click={ () => this.append(data) }>Append</el-button>
    //           <el-button size="mini" type="text" on-click={ () => this.remove(node, data) }>Delete</el-button>
    //         </span>
    //       </span>);
    //   }
    }
  };
</script>

<style>
  .custom-tree-node {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 14px;
    padding-right: 8px;
  }
  .el-tooltip__popper.is-light {
    background: #FFF;
    border: 0 !important;
}

.buttonCus{
    border: 0 !important;
    text-align: left; 
    width: 150px;
}
</style>