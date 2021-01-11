<template>
    <div>
        <button @click="modal = !modal" class="modal-button">Add Ingredients</button>
        <p>// Click on added ingredients to add them to the print list //</p>
        <teleport to="#popup">
            <div v-if="modal">
                <form @submit="addIng">
                    <input type="text" v-model="title" name="title" placeholder="Add Ingredient...">
                    <input type="submit" value="add" class="add-btn">
                    <button @click="submitCancel">cancel</button>
                </form>
            </div>
        </teleport>
    </div>
</template>

<script>

import { v4 as uuidv4 } from 'uuid';



export default {
    name: "AddIngredients",
    components: {

    },
    
    data() {
        return{
            title: '',
            modal: false,
        }

    },
    methods: {
        addIng(e) {
            e.preventDefault();
            const newIng = {
                id: uuidv4(),
                title: this.title,
            }

            this.$emit('add-ing', newIng);

            this.title = '';
            this.modal = false;
        },
        submitCancel(){
            this.modal = false;
        }
    }
    
}


</script>


<style>
.modal-button{
    width: 80px;
    height: 40px;
    
}

p {
    color: #b3b3b3;
}


</style>