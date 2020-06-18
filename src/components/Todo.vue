<template>
  <div class="todo">
    <h2>Todo</h2>
    <ul class="todo-list">
      <li v-for="(item, index) in items" :key="index">
        <p class="item-title">{{ item.title }}</p>
        <button class="close" @click="deleteItem(index)">
          X
        </button>
      </li>
    </ul>
    <div class="actions">
      <input type="text" v-model="newItemText" placeholder="New item name..." required >
      <button class="btn add-button" @click="addItem">Add item</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data() {
    return {
      items: [
        {
          title: "item1"
        },
        {
          title: "item2"
        },
        {
          title: "item3"
        },
        {
          title: "item4"
        }
      ],
      newItemText: ""
    };
  },
  methods: {
    deleteItem(index) {
      this.items.splice(index, 1);
    },
    addItem() {
      if (this.newItemText.trim().length) {
        this.items.push({
          title: this.newItemText.trim()
        })
        this.newItemText = "";
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todo {
  max-width: 480px;
  width: 100%;
}

ul {
  list-style-type: none;
  width: 100%;
  height: 400px;
  overflow: auto;
  margin: 0 auto;
  padding: 20px 10px 0;
  background-color: #346e94;
}

ul li {
  width: 100%;
  display: flex;
  background: white;
  border-radius: 2px;
  padding: 5px 20px;
  margin-bottom: 10px;
  justify-content: space-between;
  align-items: center;
}

.item-title {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  width: 100%;
  text-align: left;
}

.close {
  width: 25px;
  height: 25px;
  cursor: pointer;
  background-color: #346e94;
  color: white;
  border: 0;
  border-radius: 4px;
  font-size: 12px;
}

.close:hover {
  background-color: #4288b5;
}

.actions {
  margin-top: 20px;
  display: flex;
  justify-content: space-between;
}
</style>
