<script setup>

import { reactive } from 'vue';

</script>

<template>

  <main>
    <header>
      <h1>Memo</h1>
      <button>+</button>
    </header>

    <section>

      <div class="content">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta culpa pariatur expedita ipsum quae autem,
          obcaecati, beatae fuga eos officiis, non ut possimus cumque quaerat consectetur saepe ea sunt sed.</p>
        <p>12/12/2023</p>
      </div>

    </section>
  </main>

  <div class="modal">
    <div class="content-modal">
      <button class="btn-close">X</button>
      <textarea class="modal-text" name="modal" cols="30" rows="10"></textarea>
      <button class="btn-save">Save</button>
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
  border-radius: 5px;
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
  background-color: rgb(212, 212, 212);
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
  background-color: rgb(192, 192, 192);
  font-size: large;
}

</style>