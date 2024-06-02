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
      [Memo]
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
</style>