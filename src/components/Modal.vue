<template>
  <div @click.self="closeModal" class="backdrop">
    <div class="modal" :class="{sale:theme==='sale'}">
        <slot></slot>
        <div class="actions">
            <slot name="links"></slot>
            
        </div>

    </div>
  </div>
</template>

<script>
export default {
    props:['theme'],
    // props:['header','text','theme'],
    methods:{
        closeModal(){
            this.$emit('close')

        }
    }

}
</script>

<style >
.modal{
    width:400px;
    padding:20px;
    margin:100px auto;
    background: #fff;
    border-radius: 10px;
}
.backdrop{
    top:0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width:100%;
    height:100%
}
 .modal h1{
    color:darkcyan;
}
.sale{
    background-color:salmon;
    color:#FFF;
}
.dark{
    background-color: #000;
    
}

</style>