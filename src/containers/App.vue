<template>
  <div class="w-full h-full bg-dark-blue flex p-4">
    <transition name="fade">
      <AdviceCard
        v-if="adviceData.advice"
        :id="adviceData.id"
        :advice="adviceData.advice"
        :key="adviceData.id"
      >
        <CustomButton @handleGetAdvice="handleGetAdvice" />
      </AdviceCard>
    </transition>
  </div>
</template>

<script setup>
import CustomButton from "../components/CustomButton.vue";
import AdviceCard from "../components/AdviceCard.vue";
import { ref, onMounted } from "vue";
import axios from "axios";

const adviceData = ref({});

const handleGetAdvice = () => {
  adviceData.value = {};

  setTimeout(() => {
    axios
      .get("https://api.adviceslip.com/advice")
      .then((result) => (adviceData.value = result.data.slip))
      .catch((error) => console.error(error));
  }, 500);
};

onMounted(() => {
  handleGetAdvice();
});
</script>
<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
