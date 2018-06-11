<template>
  <div class="singleItem">
    <div @click="toggleEdit(true)" class="stringDiv">
      <div v-if="editIsOn">
        <input type="text" v-model="name">

      </div>
      
      <div v-else>
        Name: {{name}}
      </div>
      
    </div>
    <div @click="toggleEdit(true)" class="stringDiv">
      <div v-if="editIsOn">
        <input type="text" v-model="price">

      </div>
      
      <div v-else>
        Price: ${{price}}
      </div>
      
    </div>
    
   
    <br>
    <div @click="deleteItem" class="buttonSimple">DELETE</div>
    <div v-if="editIsOn">
      <div @click="toggleEdit(false)" class='stringDiv editButton'>FINISH EDIT</div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      editIsOn: false
    };
  },
  methods: {
    toggleEdit(onoff) {
      this.editIsOn = onoff
    },
    deleteItem(){
      this.listRef.deleteItem.call(this.listRef, this.index)
    }
  },
  name: "ShoppingItem",
  props: {
    listRef: Object,
    name: String,
    price: String,
    index: Number
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
.singleItem {
  margin: 5px;
  border: 6px solid black;
  display: flex;
  flex-wrap: wrap;

  background-color: powderblue;
}

.buttonSimple {
  width: 100%;
  font-weight: bold;
  border-bottom: 6px solid yellow;
}

.stringDiv {
  width: 50%;
  margin-bottom: 10px;
  border-bottom: 6px solid grey;
  margin-top: 6px;
}

.editButton {
  border: 6px solid green;
}
</style>

