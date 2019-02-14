<template>
<div class="member">
  <div class="choose">
<van-tree-select
  :items="items"
  :main-active-index="mainActiveIndex"
  :active-id="activeId"
  @navclick="onNavClick"
  @itemclick="onItemClick"
  :height="300"
/>
  </div>


</div>
</template>

<script>
export default {
  data:()=>({
  items:[
  {
    // 导航名称
    text: '所有城市',
    // 该导航下所有的可选项
    children: [
      {
        // 名称
        text: '温州',
        // id，作为匹配选中状态的标识
        id: 1,
        // 禁用选项
        disabled: true
      },
      {
        text: '杭州',
        id: 2
      }
    ]
  },
  {
    // 导航名称
    text: '浙江',
    // 该导航下所有的可选项
    children: [
      {
        // 名称
        text: '温州',
        // id，作为匹配选中状态的标识
        id: 1,
        // 禁用选项
       
      },
      {
        text: '杭州',
        id: 2
      },  {
        // 名称
        text: '丽水',
        // id，作为匹配选中状态的标识
        id: 3,
        // 禁用选项
       
      },
        {
        // 名称
        text: '金华',
        // id，作为匹配选中状态的标识
        id: 4,
        // 禁用选项
       
      },
        {
        // 名称
        text: '义乌',
        // id，作为匹配选中状态的标识
        id: 5,
        // 禁用选项
       
      },
        {
        // 名称
        text: '横店',
        // id，作为匹配选中状态的标识
        id: 6,
        // 禁用选项
       
      },
        {
        // 名称
        text: '嘉兴',
        // id，作为匹配选中状态的标识
        id: 7,
        // 禁用选项
       
      },
       {
        // 名称
        text: '德兴',
        // id，作为匹配选中状态的标识
        id: 8,
        // 禁用选项
       
      },
       {
        // 名称
        text: '宁波',
        // id，作为匹配选中状态的标识
        id: 9,
        // 禁用选项
       
      },
       {
        // 名称
        text: '绍兴',
        // id，作为匹配选中状态的标识
        id: 10,
        // 禁用选项
       
      },
       {
        // 名称
        text: '舟山',
        // id，作为匹配选中状态的标识
        id: 11,
        // 禁用选项
       
      },
    ]
  },
],
      // 左侧高亮元素的index
      mainActiveIndex: 0,
      // 被选中元素的id
      activeId: 1
  }),
  
  methods:{
   onNavClick(index) {
      this.mainActiveIndex = index;
    },
    onItemClick(data) {
      this.activeId = data.id;
    }
  }
}
</script>
<style  lang="less">
  .choose{
    margin-top: 100px
  }
</style>