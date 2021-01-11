<template>
    <div  class="left-menu">
        <Ingredients @itemselect="sendingIng" />
    </div>
</template>


<script>
import Ingredients from "./Ingredients"

export default {
    name: "Selectionpanel",
    components: {
        Ingredients, 
    },

    
    methods: {
        sendingIng(ing){
            this.$emit('itemselecttwo', ing)
        }
    }
}
</script>


<style>
.left-menu {
    border: 5px solid gray;
    padding: 5px 5px;
}


</style>