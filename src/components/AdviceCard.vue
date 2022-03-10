<template>
  <div class="m-auto w-full max-w-[540px] relative">
    <div
      class="w-full bg-dark-grayish-blue rounded-[15px] mb-8 flex flex-col items-center text-center pt-10 px-7 pb-16"
    >
      <h1
        class="text-neon-green uppercase tracking-[0.3em] text-[0.688rem] md:text-[0.813rem]"
      >
        Advice #{{ id }}
      </h1>
      <p
        class="text-light-cyan w-full max-w-[440px] mt-8 mb-6 text-2xl md:mb-8 text-[1.75rem]"
      >
        "{{ advice }}"
      </p>
      <img
        class="md:hidden"
        src="../assets/pattern-divider-mobile.svg"
        alt="Pattern Divider Mobile"
      />
      <img
        class="hidden md:block"
        src="../assets/pattern-divider-desktop.svg"
        alt="Pattern Divider Mobile"
      />
    </div>
    <slot></slot>
  </div>
</template>

<script setup>
defineProps({
  id: {
    type: Number,
    required: true,
  },
  advice: {
    type: String,
    required: true,
  },
});
</script>
