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
      
      <div>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta culpa pariatur expedita ipsum quae autem, obcaecati, beatae fuga eos officiis, non ut possimus cumque quaerat consectetur saepe ea sunt sed.</p>
        <p>12/12/2023</p>
      </div>
      
    </section>
  </main>

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

div {
  width: 30%;
  padding: 15px;
  background-color: rgb(124, 202, 204);
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  border-radius: 5px;
}

</style>