<script setup>
import { defineProps } from "vue";

const props = defineProps({
  buttonText: String,
  isActive: Boolean
});
</script>

<template>
    <a :class="['btn-section', 'text-uppercase', { 'active': isActive }]">
        {{ buttonText }}
    </a>
</template>

<style scoped>
.btn-section {
    color: var(--font-color);
    font-size: 14px;
    padding: 4px 16px;
    border-radius: 8px;
}

.btn-section:hover {
    color: var(--white-color);
    background-color: #57acd7;
    transition: 0.3s;
}

.active {
    color: var(--white-color);
    background-color: var(--primary-color);
    border: 0.5px solid #7EAFD4;
}
</style>