<template>
<div class="member">
<van-tabs v-model="active" swipeable>
            <van-tab v-for="(item,index) in navArr" :title="item.name" class="v-tab" :key="index">
                <div v-if="index==0">
                    我是第一个
                </div>
                <div v-if="index==1">我是二个</div>
                <div v-if="index==2">我是第三个</div>
            </van-tab>
 
 </van-tabs>


</div>
</template>

<script>
export default {
  data:()=>({
    
           

  
  })
}
</script>
<style  lang="less">
  
</style>