<template>
  <div class="searchInput">
    <input type="text" class="inp" placeholder="오늘의 할일을 입력하세요"
    v-model="newTodoItem">
    <div class="btn" @click="todoItem">할일</div>
    <div class="clearAll" @click="$emit('clearAll')">전체삭제</div>
    

  </div>
  <transition name="mView">
  <modal v-if="modalView" @click="modalView= false">
    <template v-slot:header>경고</template>
    <template v-slot:body>오늘의 할일을 입력하세요</template>
  </modal>
  </transition>
</template>

<script>
import Modal from "@/components/Modal.vue";

export default {
    components:{
        Modal
    },
data(){
    return{
        newTodoItem:"",
        modalView:false,
    }
},
methods:{
    todoItem(){
        if(this.newTodoItem != ""){

            let value=this.newTodoItem && this.newTodoItem.trim();
        this.$emit("additem",value)
        }else{
            this.modalView = true;

        }
        this.newTodoItem = "";
    }
}
}
</script>

<style lang="scss">
  .searchInput{height: 100px;
    position: relative;
    input{margin-right: 20px;height: 40px;
    width: 85%;margin-bottom: 10px;padding: 5px;


    }
    .btn{width: 35%;position: absolute;padding: 5px;
    background: #607EAA;display: flex;color: white;
    justify-content: center;align-items: center;
    border: 0 none;border-radius: 5px;}
    .clearAll{
        width: 35%;position: absolute;padding: 5px;
    background: rgb(255, 226, 226);display: flex;color: rgb(255, 6, 6);
    justify-content: center;align-items: center;
    border: 0 none;border-radius: 5px;font-weight: 600;right: 15%;
        }
  }
</style>