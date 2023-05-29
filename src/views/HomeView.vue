<script setup lang="ts">
</script>

<template>
  <div class="greetings">
    <h1>Want to train your creativity mental visualization skills?</h1>
    <h1>For better imagination during <span class="green">learning or meditation</span></h1>
    <div class="welcomePageLinks">
      <RouterLink to="/modes/simple">
        <h2>Simple ></h2>
      </RouterLink>
      <!-- <RouterLink to="/modes/image-extension">
        <h2>Image extension</h2>
      </RouterLink> -->
    </div>
  </div>
</template>


<style scoped>
h1 {
  font-weight: 500;
  font-size: clamp(1.5rem, 2.5vw, 4rem); 
  top: -10px;
}

h2 {
  font-size: 1.2rem;
}

.greetings {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding-bottom: 15%;
}

.greetings {
  text-align: center;
}

.welcomePageLinks {
  margin-top: 2rem;
  display: flex;
  gap: 3rem;

}
</style>

