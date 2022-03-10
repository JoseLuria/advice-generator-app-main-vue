<template>
  <button
    @click="handleRandomAdvice"
    class="h-16 w-16 rounded-full bg-neon-green flex absolute bottom-0 left-[50%] translate-x-[-50%]"
  >
    <img class="m-auto" src="../assets/icon-dice.svg" alt="Dice Icon" />
  </button>
</template>

<script setup>
const emit = defineEmits(["handleGetAdvice"]);

const handleRandomAdvice = () => {
  emit("handleGetAdvice");
};
</script>
