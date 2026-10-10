<template>
  <div id="app">
    <header>
      <h1>Welcome to Ramzy</h1>
      <p>A modern Vite + Vue 3 application</p>
    </header>
    <main>
      <button @click="count++">Count: {{ count }}</button>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<style scoped>
#app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

header {
  margin-bottom: 2rem;
}

h1 {
  color: #333;
  font-size: 2.5rem;
}

p {
  color: #666;
  font-size: 1.1rem;
}

button {
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
  background: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background 0.2s;
}

button:hover {
  background: #359268;
}
</style>
