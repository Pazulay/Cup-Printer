<template>
    <div>
        <AddIngredients v-on:add-ing="addIng" />
        <ul>
            <li @click="sendingIng(ing)" class="ing-items" v-for="ing in ingredients" v-bind:key="ing.id">
                {{ ing.title }}
            </li>
        </ul>
    </div>
</template>


<script>
import AddIngredients from "./AddIngredients"

export default {
    name: 'Ingredients',
    components: {
        AddIngredients
    },
    data() {
        return {
            ingredients: [],

        }
    },

    methods: {
        addIng(newIng) {
            this.ingredients = [...this.ingredients, newIng];
        },

        supSupp(){
            console.log('hi');
        },

        // copyIng(ing){
        //     this.ingredients2 = [...this.ingredients2, ing];
        // },

        sendingIng(ing) {
            this.$emit('itemselect', ing)
        },

    },

    
}       
</script>



<style>
.ing-items {
    background-color: #b3b3b3;
}



</style>