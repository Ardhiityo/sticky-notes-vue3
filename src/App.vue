<script setup>
import { ref } from "vue";

const showItem = ref(false);
const newMemo = ref("");
const itemMemo = ref([]);
const errorMessage = ref("");

function addItem() {
  if (!newMemo.value) return (errorMessage.value = "Please enter a memo!");
  itemMemo.value.push({
    id: Date.now(),
    memo: newMemo.value,
    color: addColor(),
    date: new Date().toLocaleString("id-ID"),
  });
  newMemo.value = "";
  showItem.value = false;
}

function addColor() {
  return `#${Math.floor(Math.random() * 16777215).toString(16)}`;
}

function deleteItem(id) {
  return (itemMemo.value = itemMemo.value.filter((item) => item.id !== id));
}
</script>

<template>
  <main>
    <header>
      <h1>Memo</h1>
      <button @click="showItem = !showItem">+</button>
    </header>

    <section>
      <div
        v-for="(item, index) in itemMemo"
        :key="index"
        class="content"
        :style="{ backgroundColor: item.color }"
      >
        <p>{{ item.memo }}</p>
        <div class="footer">
          <p>{{ item.date }}</p>
          <button @click="deleteItem(item.id)">X</button>
        </div>
      </div>
    </section>
  </main>

  
  <div class="modal" v-if="showItem">
    <div class="content-modal">
      <p v-if="!newMemo" class="error-message">{{ errorMessage }}</p>
      <button class="btn-close" @click="showItem = !showItem">X</button>
      <textarea
        class="modal-text"
        v-model="newMemo"
        name="modal"
        cols="30"
        rows="10"
      ></textarea>
      <button class="btn-save" @click="addItem()">Save</button>
    </div>
  </div>
</template>

<style scoped>
main {
  max-width: 900px;
  min-height: 100vh;
  margin: 20px auto;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 50px;
}

header h1 {
  color: rgb(80, 80, 80);
}

header button {
  border: none;
  padding: 10px 20px;
  font-size: xx-large;
  border-radius: 100%;
  cursor: pointer;
  background-color: rgb(125, 204, 207);
}

section {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.content {
  width: 30%;
  padding: 15px;
  background-color: rgb(124, 202, 204);
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  border-radius: 5px;
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
}

.modal {
  background-color: rgba(234, 175, 175, 0.29);
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.content-modal {
  background-color: white;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 40%;
  padding: 30px;
  height: 50%;
  box-sizing: border-box;
  border-radius: 10px;
}

.btn-close {
  position: absolute;
  top: 5px;
  right: 5px;
  border: none;
  padding: 5px 8px;
  border-radius: 4px;
  cursor: pointer;
  background-color: transparent;
  font-size: large;
}

.modal-text {
  width: 100%;
  height: 100%;
  border-radius: 5px;
}

.btn-save {
  margin-top: 10px;
  display: flex;
  width: 100%;
  padding: 10px;
  border-radius: 4px;
  display: flex;
  justify-content: center;
  border: none;
  cursor: pointer;
  background-color: rgb(178, 178, 178);
  font-size: large;
}

.error-message {
  color: red;
}
</style>