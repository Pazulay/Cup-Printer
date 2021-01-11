<template>
  <div>
    <Selectionpanel @itemselecttwo="takeIng" />
    <Rightpanel :itempackage="itemstosend" @deletesignal="deletePrintItem" />
  </div>
</template>

<script>
import Selectionpanel from "./components/Selectionpanel"
import Rightpanel from "./components/Rightpanel"

export default {
  name: 'App',
  components: {
    Selectionpanel,
    Rightpanel,
  },

  data(){
    return {
      itemstosend: [],



    }

  },

  methods: {
    takeIng(ing){
      this.itemstosend = [...this.itemstosend, ing]
    },

    deletePrintItem(index){
      this.itemstosend.splice(index, 1);
    }


  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  background-color: #181818;
}
</style>
