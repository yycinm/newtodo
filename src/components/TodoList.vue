<template>
  <ul>
    <li v-for="(item,i) in todoItem" :key="i" class="itemList">
        <div class="list">

        {{item}}
        </div>
        <div class="del" @click="removeDel(i,item)">
           <i class="fa-regular fa-square-minus"></i>
        </div>
    </li>
  </ul>
</template>

<script>
export default {
    props:[
        "todoItem"
    ],
    methods:{
        removeDel(num,item){
            this.$emit("reDel",num,item)
        }
    }

}
</script>

<style lang="scss">
 .itemList{width: 85%;background: #F9F5EB;
 color: #333;display: flex;border-bottom: 1px solid  rgb(32, 84, 119);
position: relative;font-weight: normal;
 padding: 20px;
 .del{
    width: 20px;
    position: absolute;right: 0;padding: 5px 20px;
   color: rgb(35, 125, 185);;display: flex;justify-content: center;align-items: center;
   }
   .list{
    
   }
 }
</style>