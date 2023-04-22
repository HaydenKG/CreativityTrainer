<script setup lang="ts">
</script>

<template>
    <div class="content">
        <h1>Imagine these two together:</h1>
        <h1><span class="green">Banana</span> watching <span class="green">TV</span></h1>
    </div>
</template>

<style scoped>
h1 {
    font-weight: 500;
    font-size: 2.6rem;
    top: -10px;
}

h3 {
    font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
    text-align: center;
}

@media (min-width: 1024px) {

    .greetings h1,
    .greetings h3 {
        text-align: left;
    }
}
</style>
