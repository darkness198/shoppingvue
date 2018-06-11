<template>

  <div>
    <h1>Shopping List</h1>
    <label for="">Item Name</label>
    <input placeholder='Enter new item name' v-model="newItemName" type="text">

    <label for="">Item Price</label>
    <input placeholder='Enter new item price' t v-model="newItemPrice" type="text">

    <button @click="addItem">Add Item</button>
    <ul class="listContainer">
      <ShoppingItem :listRef="getThisRef()" v-for="(item, index) in itemsArr" :name="item.name" :price="item.price" :index="index" :key="item.name+index" class="listItem"></ShoppingItem >
    </ul>


  </div>

    
 
</template>

<script>
import ShoppingItem from "./ShoppingItem.vue";
export default {
  methods: {
    addItem() {
      this.itemsArr.push({name: this.newItemName, price: this.newItemPrice})
      this.newItemName = '';
      this.newItemPrice = '';
    },
    deleteItem(index) {
      this.itemsArr.splice(index, 1)
    }
  },
  data() {
    return {
      newItemName: '',
      newItemPrice: '',
      itemsArr: [
        {name: 'Bananas', price: '3.75'},
        {name: 'Sugar', price: '5.42'}, 

      ],
      getThisRef() {
        return this;
      }
    }
  },
  components: {
    ShoppingItem
  }
}
</script>



<style scoped>
.listContainer {
  justify-content: space-between;
  width: 80%;
  height: 80%;
  display: flex;
  flex-wrap: wrap;
}
</style>
