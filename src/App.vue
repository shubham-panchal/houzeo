<script setup>
import Header from "./components/Header.vue";
import SubHeader from "./components/SubHeader.vue";
import Home from "./components/Home.vue";
</script>

<template>
  <div class="root-container">
    <nav class="nav-section">
      <Header />
      <SubHeader />
    </nav>
    <main class="main-container">
      <Home />
    </main>
  </div>
</template>

<style>
.root-container {
  font-family: "Poppins", sans-serif;
}

/* utility classes */
.cta {
  outline: none;
  border: none;
  background-color: transparent;
}

.cursor-pointer {
  cursor: pointer;
}

@keyframes pulse {
  0% {
    box-shadow: 0px 0px 0px 0px rgba(11, 90, 165, 1);
  }

  100% {
    box-shadow: 0px 0px 0px 30px rgba(11, 90, 165, 0);
  }
}
</style>
