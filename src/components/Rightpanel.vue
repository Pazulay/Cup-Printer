<template>
    <div class="right-menu2">
        <!-- <button @click="myFilter">test</button> -->
        <h1>LIST</h1>
        <ul>
            <li class="print-items" id="printMe"  v-for="(items) in itempackage" v-bind:key="items.id">
                <h3> {{ items.title }}</h3>
                <button @click="sendItemToDelete">remove</button>
            </li>
        </ul>

        <button @click="printDiv">Print</button>
    </div>
</template>




<script>


export default {
    name: "Rightpanel",
    components: {

    },

    props: [
        'itempackage'
    ],
    
    data() {
        return {
            
        }
    },

    methods: {
        printDiv(){
            const localOptions = {
                styles: [
                    'https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css',
                ]
            };
            this.$htmlToPaper('printMe', localOptions);
        },

        sendItemToDelete(index){
            this.$emit('deletesignal', index);
        },

        // myFilter(items, index, itempackage){
        //     for(var i=0; i < index; i++){
        //         if(itempackage[i].title === items.title) {
        //             return false;
        //         }
        //     }
        //     return true;
        // }



    }


}
</script>



<style>

h1 {
    color: #b3b3b3;
}

.right-menu2{
    border: 5px solid #b3b3b3;
    padding: 5px;
}

.print-items {
    color: #b3b3b3;
}



</style>