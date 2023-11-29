<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  teacherAchievement: String,
});
</script>

<template>
  <div class="me-2 d-flex align-items-center">
      <i class="bi bi-star-fill text-warning me-1 teacher-headline-icon"></i>
      <span class="professor-headline-achievement">{{ teacherAchievement }}</span>
  </div>
</template>

<style scoped>
.teacher-achievement {
  font-size: 12px;
  color:#707070;
}

.teacher-headline-icon {
  font-size: 14px;
}
</style>