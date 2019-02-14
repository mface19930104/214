<template>
  <div class="getimages">
    <van-tabs  v-model="active" swipeable @click="onClick" @change="onChange"  >
      <van-tab v-for="item in cate" :title="item.title " :key="item.id"   >
        <div v-for="item in imageList" :title="item.title" :key="item.id">
           <router-link tag="div" :to="'/home/photoinfo'+item.id">
            <img  v-lazy="item.img_url"  >
    </router-link>
        </div>
        </van-tab>
    </van-tabs>
   <!-- <van-tabs v-model="active" animated @click="onClick">
      <van-tab v-for="item in listpho" :title="item.title" :key="item.id">
        <div v-for="item in listImages" :title="item.title" :key="item.id">
          <router-link tag="div" :to="'/index/photoinfo/'+item.id" class="listpos">
            <img :src="item.img_url" alt>
            <div class="pholist">
              <p>{{item.title}}</p>
              <p>{{item.zhaiyao}}</p>
            </div>
          </router-link>
        </div>
      </van-tab>
    </van-tabs> -->

 
  </div>
</template>
<script>
export default {
  data:()=>({
    cate:[],
    imageList:[],
    active:0,
   

  }),
  created(){
    this.getCate(),
    this.getImg(0)
  },
  methods:{
    getCate(){
      this.$axios.get('api/getimgcategory').then((res)=>{
       if (res.data.status===0) {
         this.cate=res.data.message;
         this.cate.unshift({ title:'全部', id:0 })
         console.log(this.cate);
         
       }
        
      })
    },
    getImg(cateId){
      this.$axios.get('api/getimages/'+cateId).then((res)=>{
    this.imageList=res.data.message;
        console.log(this.imageList);
        
      })
    },
      onClick(index) {
     this.getImg(index)
    
    
    },
   onChange(index){
          this.getImg(index)
   }
  }
};
</script>
<style lang="less">
</style>
