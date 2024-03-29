<template>
  <div class="app">
    <Sidebar />
    <main>
      <router-view />
    </main>
  </div>
</template>


<script setup>
import Sidebar from './components/Sidebar.vue';
</script>

<style lang="scss">
:root {
  --palette-one: #0081a7;
  --palette-two: #00afb9;
  --palette-three: #fdfcdc;
  --palette-four: #fed9b7;
  --palette-five: #f07167;
  --sidebar-width: 300px;
  --primary: #4ade80;
  --primary-alt: #22c55e;
  --grey: #64748b;
  --dark: #1e293b;
  --dark-alt: #334155;
  --light: #f1f5f9;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira sans', sans-serif;
}

body {
  font-family: 'Poppins', sans-serif;
  background-color: var(--palette-three);
}

.app {
  display: flex;

  main {
    flex: 1 1 0;
    padding: 2rem;

    @media (max-width: 768px) {
      padding: 6rem;
    }
  }
}
</style>