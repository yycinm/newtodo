<template>
<div class="modal">

  <h3>
    <slot name="header"></slot>
  </h3>
  <h4>
    <slot name="body"></slot>
  </h4>
    <div>

    <button>닫기</button>
    
    </div>
</div>

</template>

<script>
export default {

}
</script>

<style lang="scss">
    .modal{
        position: absolute;
        top: 100px;
        left: 50%;
        transform: translateX(-50%);
        background: white;
        padding: 30px;
        box-shadow: 5px 5px 5px rgba(0,0,0,0.5);

        div{
            padding: 10px;position: relative;
            button{
                position: absolute;right: 0;
            }
            
    }
        
    }
    
</style>